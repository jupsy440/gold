<script setup lang="ts">
const products = [
  {
    name: 'Premium Crypto Course',
    description: 'Learn how to invest in cryptocurrencies like a pro',
    link: 'https://keystoneinvestors.com/event-24/?utm_source=ds24&utm_medium=email&utm_campaign=[AFFILIATE]#aff=Cashchampionchannel',
    image: 'https://images.unsplash.com/photo-1639762681057-408e52192e55?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2232&q=80'
  },
  {
    name: 'Crypto Trading Signals',
    description: 'Get professional trading signals for top cryptocurrencies',
    link: 'https://keystoneinvestors.com/event-24/?utm_source=ds24&utm_medium=email&utm_campaign=[AFFILIATE]#aff=Cashchampionchannel',
    image: 'https://images.unsplash.com/photo-1621761191319-c6fb62004040?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2787&q=80'
  },
  {
    name: 'Portfolio Management',
    description: 'Let experts manage your crypto portfolio',
    link: 'https://keystoneinvestors.com/event-24/?utm_source=ds24&utm_medium=email&utm_campaign=[AFFILIATE]#aff=Cashchampionchannel',
    image: 'https://images.unsplash.com/photo-1639762681057-408e52192e55?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2232&q=80'
  }
]
</script>

<template>
  <div class="products-tab">
    <h1>Our Investment Products</h1>
    <p>Choose from our carefully selected crypto investment products</p>
    
    <div class="product-grid">
      <div v-for="(product, index) in products" :key="index" class="product-card">
        <img :src="product.image" :alt="product.name" class="product-image">
        <div class="product-info">
          <h3>{{ product.name }}</h3>
          <p>{{ product.description }}</p>
          <a :href="product.link" target="_blank" class="product-link">Learn More</a>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.products-tab {
  max-width: 1200px;
  margin: 0 auto;
  text-align: center;
}

.products-tab h1 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
  color: #3498db;
}

.products-tab p {
  font-size: 1.2rem;
  color: #7f8c8d;
  margin-bottom: 2rem;
}

.product-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}

.product-card {
  background: white;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  transition: transform 0.3s ease;
}

.product-card:hover {
  transform: translateY(-5px);
}

.product-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.product-info {
  padding: 1.5rem;
  text-align: left;
}

.product-info h3 {
  color: #3498db;
  margin-bottom: 0.5rem;
}

.product-info p {
  color: #7f8c8d;
  font-size: 1rem;
  margin-bottom: 1rem;
}

.product-link {
  display: inline-block;
  background: #f1c40f;
  color: #2c3e50;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  text-decoration: none;
  transition: background 0.3s ease;
}

.product-link:hover {
  background: #f39c12;
}
</style>
