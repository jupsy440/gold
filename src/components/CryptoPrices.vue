<script setup lang="ts">
interface CryptoPrice {
  name: string
  image: string
  current_price: number
  price_change_percentage_24h: number
}

defineProps<{
  prices: CryptoPrice[]
}>()
</script>

<template>
  <div class="crypto-prices">
    <h2>Live Crypto Prices</h2>
    <div class="price-grid">
      <div v-for="(crypto, index) in prices" :key="index" class="price-card">
        <div class="crypto-info">
          <img :src="crypto.image" :alt="crypto.name" class="crypto-icon">
          <span class="crypto-name">{{ crypto.name }}</span>
        </div>
        <div class="price-info">
          <span class="price">${{ crypto.current_price.toLocaleString() }}</span>
          <span 
            class="price-change" 
            :class="{ positive: crypto.price_change_percentage_24h > 0, negative: crypto.price_change_percentage_24h < 0 }"
          >
            {{ crypto.price_change_percentage_24h.toFixed(2) }}%
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.crypto-prices {
  background: white;
  border-radius: 8px;
  padding: 1.5rem;
  margin-top: 2rem;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.crypto-prices h2 {
  color: #1a1a2e;
  margin-bottom: 1rem;
  text-align: center;
}

.price-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 1rem;
}

.price-card {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.5rem;
  border-radius: 4px;
  background: #f8f9fa;
}

.crypto-info {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.crypto-icon {
  width: 24px;
  height: 24px;
}

.crypto-name {
  font-weight: 500;
}

.price-info {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}

.price {
  font-weight: bold;
}

.price-change {
  font-size: 0.8rem;
}

.positive {
  color: #4caf50;
}

.negative {
  color: #f44336;
}
</style>
