<script setup lang="ts">
</script>

<template>
  <div class="home-tab">
    <h1>Welcome to CryptoInvestEasy</h1>
    <p>Your trusted partner in cryptocurrency investments</p>
    
    <div class="features">
      <div class="feature-card">
        <h3>Easy Investing</h3>
        <p>Simple tools to start your crypto journey</p>
      </div>
      <div class="feature-card">
        <h3>Expert Analysis</h3>
        <p>Professional market insights</p>
      </div>
      <div class="feature-card">
        <h3>Secure Platform</h3>
        <p>Your investments are safe with us</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.home-tab {
  text-align: center;
  max-width: 1200px;
  margin: 0 auto;
}

.home-tab h1 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
  color: #3498db;
}

.home-tab p {
  font-size: 1.2rem;
  color: #7f8c8d;
  margin-bottom: 2rem;
}

.features {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 1rem;
  margin-top: 2rem;
}

.feature-card {
  background: white;
  border-radius: 8px;
  padding: 1.5rem;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  flex: 1;
  min-width: 250px;
  transition: transform 0.3s ease;
}

.feature-card:hover {
  transform: translateY(-5px);
}

.feature-card h3 {
  color: #3498db;
  margin-bottom: 0.5rem;
}

.feature-card p {
  color: #7f8c8d;
  font-size: 1rem;
  margin: 0;
}
</style>
