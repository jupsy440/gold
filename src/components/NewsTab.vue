<script setup lang="ts">
const newsSources = [
  {
    name: 'CoinDesk',
    url: 'https://www.coindesk.com',
    description: 'Latest cryptocurrency news and analysis'
  },
  {
    name: 'Cointelegraph',
    url: 'https://cointelegraph.com',
    description: 'Bitcoin and cryptocurrency news'
  },
  {
    name: 'CryptoSlate',
    url: 'https://cryptoslate.com',
    description: 'Blockchain and cryptocurrency news'
  },
  {
    name: 'Decrypt',
    url: 'https://decrypt.co',
    description: 'Daily cryptocurrency news'
  }
]
</script>

<template>
  <div class="news-tab">
    <h1>Crypto News Sources</h1>
    <p>Stay updated with the latest in cryptocurrency</p>
    
    <div class="news-grid">
      <div v-for="(source, index) in newsSources" :key="index" class="news-card">
        <h3>{{ source.name }}</h3>
        <p>{{ source.description }}</p>
        <a :href="source.url" target="_blank" class="news-link">Visit Site</a>
      </div>
    </div>
  </div>
</template>

<style scoped>
.news-tab {
  max-width: 1200px;
  margin: 0 auto;
  text-align: center;
}

.news-tab h1 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
  color: #3498db;
}

.news-tab p {
  font-size: 1.2rem;
  color: #7f8c8d;
  margin-bottom: 2rem;
}

.news-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}

.news-card {
  background: white;
  border-radius: 8px;
  padding: 1.5rem;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  transition: transform 0.3s ease;
}

.news-card:hover {
  transform: translateY(-5px);
}

.news-card h3 {
  color: #3498db;
  margin-bottom: 0.5rem;
}

.news-card p {
  color: #7f8c8d;
  font-size: 1rem;
  margin-bottom: 1rem;
}

.news-link {
  display: inline-block;
  color: #f1c40f;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
}

.news-link:hover {
  color: #f39c12;
}
</style>
