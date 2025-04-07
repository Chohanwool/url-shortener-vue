<script setup>
import { ref } from 'vue'

const shortenedUrls = ref([])
const originalUrl = ref('')
const shortenedUrl = ref('')

const shortenUrl = () => {
  const randomString = Math.random().toString(36).substring(2, 8)
  shortenedUrl.value = `${window.location.origin}/${randomString}`
  shortenedUrls.value.unshift({
    original: originalUrl.value,
    shortened: shortenedUrl.value,
    createdAt: new Date().toISOString()
  })
  originalUrl.value = ''
}
</script>

<template>
  <div class="home-container">
    <div class="url-shortener">
      <h1>Shorten Your URL</h1>
      <div class="input-group">
        <input 
          v-model="originalUrl"
          type="text" 
          placeholder="Enter your URL here"
          class="url-input"
        />
        <button @click="shortenUrl" class="shorten-button">Shorten</button>
      </div>
      
      <div v-if="shortenedUrl" class="result">
        <p>Shortened URL:</p>
        <a :href="shortenedUrl" target="_blank">{{ shortenedUrl }}</a>
      </div>
    </div>

    <div class="recent-urls">
      <h2>Recent URLs</h2>
      <div v-if="shortenedUrls.length === 0" class="empty-state">
        No URLs shortened yet
      </div>
      <ul v-else class="url-list">
        <li v-for="(url, index) in shortenedUrls" :key="index" class="url-item">
          <div class="url-info">
            <a :href="url.original" target="_blank" class="original-url">{{ url.original }}</a>
            <a :href="url.shortened" target="_blank" class="shortened-url">{{ url.shortened }}</a>
            <span class="created-at">{{ new Date(url.createdAt).toLocaleString() }}</span>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
.home-container {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.url-shortener {
  background-color: white;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  width: 100%;
}

.url-shortener h1 {
  margin-bottom: 1.5rem;
  color: #2c3e50;
}

.input-group {
  display: flex;
  gap: 1rem;
  margin: 1rem 0;
}

.url-input {
  flex: 1;
  padding: 0.75rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 1rem;
  transition: border-color 0.3s;
}

.url-input:focus {
  outline: none;
  border-color: #3498db;
}

.shorten-button {
  padding: 0.75rem 1.5rem;
  background-color: #2c3e50;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: all 0.3s ease;
  font-weight: bold;
}

.shorten-button:hover {
  background-color: #34495e;
  transform: translateY(-1px);
}

.result {
  margin-top: 1.5rem;
  padding: 1.5rem;
  background-color: #f8f9fa;
  border-radius: 4px;
  border-left: 4px solid #3498db;
}

.result p {
  color: #7f8c8d;
  margin-bottom: 0.5rem;
}

.result a {
  color: #3498db;
  text-decoration: none;
  word-break: break-all;
}

.recent-urls {
  background-color: white;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.recent-urls h2 {
  margin-bottom: 1.5rem;
  color: #2c3e50;
}

.url-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.url-item {
  padding: 1.5rem;
  border-radius: 8px;
  background-color: #f8f9fa;
  transition: transform 0.3s ease;
}

.url-item:hover {
  transform: translateX(5px);
}

.url-info {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.original-url {
  color: #2c3e50;
  text-decoration: none;
  word-break: break-all;
}

.shortened-url {
  color: #3498db;
  text-decoration: none;
}

.created-at {
  color: #7f8c8d;
  font-size: 0.9rem;
}

.empty-state {
  text-align: center;
  color: #7f8c8d;
  padding: 3rem;
  background-color: #f8f9fa;
  border-radius: 8px;
}

@media (max-width: 768px) {
  .input-group {
    flex-direction: column;
  }

  .shorten-button {
    width: 100%;
  }

  .url-item {
    padding: 1rem;
  }
}
</style>
