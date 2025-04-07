<script setup>
import { ref } from 'vue'

const myUrls = ref([])
</script>

<template>
  <div class="my-urls-container">
    <h1>My URLs</h1>
    <div v-if="myUrls.length === 0" class="empty-state">
      You haven't shortened any URLs yet
    </div>
    <ul v-else class="url-list">
      <li v-for="(url, index) in myUrls" :key="index" class="url-item">
        <div class="url-info">
          <a :href="url.original" target="_blank" class="original-url">{{ url.original }}</a>
          <a :href="url.shortened" target="_blank" class="shortened-url">{{ url.shortened }}</a>
          <span class="created-at">{{ new Date(url.createdAt).toLocaleString() }}</span>
        </div>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.my-urls-container {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.my-urls-container h1 {
  color: #2c3e50;
  margin-bottom: 1rem;
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
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
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
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

@media (max-width: 768px) {
  .url-item {
    padding: 1rem;
  }
}
</style> 