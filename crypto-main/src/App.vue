<script setup lang="ts">
import { ref, onMounted } from 'vue'
import HomeTab from './components/HomeTab.vue'
import ProductsTab from './components/ProductsTab.vue'
import NewsTab from './components/NewsTab.vue'
import CryptoPrices from './components/CryptoPrices.vue'

const activeTab = ref('home')
const cryptoData = ref([])
const email = ref('')

const fetchCryptoPrices = async () => {
  try {
    const response = await fetch('https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&order=market_cap_desc&per_page=10&page=1&sparkline=false')
    cryptoData.value = await response.json()
  } catch (error) {
    console.error('Error fetching crypto data:', error)
  }
}

const subscribe = () => {
  alert(`Thank you for subscribing with ${email.value}!`)
  email.value = ''
}

onMounted(() => {
  fetchCryptoPrices()
  setInterval(fetchCryptoPrices, 60000)
})
</script>

<template>
  <header class="header">
    <div class="logo">CryptoInvestEasy</div>
    <nav class="tabs">
      <button 
        @click="activeTab = 'home'" 
        :class="{ active: activeTab === 'home' }"
      >
        Home
      </button>
      <button 
        @click="activeTab = 'products'" 
        :class="{ active: activeTab === 'products' }"
      >
        Investment Products
      </button>
      <button 
        @click="activeTab = 'news'" 
        :class="{ active: activeTab === 'news' }"
      >
        Crypto News
      </button>
    </nav>
  </header>

  <main class="main-content">
    <HomeTab v-if="activeTab === 'home'" />
    <ProductsTab v-if="activeTab === 'products'" />
    <NewsTab v-if="activeTab === 'news'" />
    
    <CryptoPrices :prices="cryptoData" />
  </main>

  <footer class="footer">
    <div class="newsletter">
      <h3>Subscribe to our newsletter</h3>
      <div class="subscribe-form">
        <input 
          v-model="email" 
          type="email" 
          placeholder="Your email address" 
          required
        >
        <button @click="subscribe">Subscribe</button>
      </div>
    </div>
    <div class="copyright">
      &copy; 2023 CryptoInvestEasy. All rights reserved.
    </div>
  </footer>
</template>

<style scoped>
.header {
  background: #3498db;
  color: white;
  padding: 1rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.logo {
  font-size: 1.5rem;
  font-weight: bold;
}

.tabs button {
  background: none;
  border: none;
  color: white;
  padding: 0.5rem 1rem;
  margin-left: 1rem;
  cursor: pointer;
  font-size: 1rem;
  transition: all 0.3s ease;
}

.tabs button:hover {
  color: #f1c40f;
}

.tabs button.active {
  color: #f1c40f;
  border-bottom: 2px solid #f1c40f;
}

.main-content {
  padding: 2rem;
  min-height: 70vh;
  background-color: #f8f9fa;
}

.footer {
  background: #3498db;
  color: white;
  padding: 2rem;
  text-align: center;
}

.newsletter {
  margin-bottom: 1rem;
}

.subscribe-form {
  display: flex;
  justify-content: center;
  gap: 0.5rem;
  margin-top: 1rem;
}

.subscribe-form input {
  padding: 0.5rem;
  width: 300px;
  border: none;
  border-radius: 4px;
}

.subscribe-form button {
  background: #f1c40f;
  color: #2c3e50;
  border: none;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  cursor: pointer;
  transition: background 0.3s ease;
}

.subscribe-form button:hover {
  background: #f39c12;
}

.copyright {
  margin-top: 1rem;
  font-size: 0.9rem;
  color: #ecf0f1;
}
</style>
