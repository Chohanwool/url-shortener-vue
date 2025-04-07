<script setup>
import { RouterView } from 'vue-router'
import AppNavbar from './components/AppNavbar.vue'
</script>

<template>
  <div class="app-container">
    <AppNavbar />
    <main class="main-content">
      <RouterView />
    </main>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html, body {
  height: 100%;
  width: 100%;
}

body {
  background-color: #f5f6fa;
  font-family: Arial, sans-serif;
  line-height: 1.6;
}

.app-container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  width: 100%;
}

.main-content {
  flex: 1;
  padding: 2rem;
  width: 100%;
  max-width: 100%;
  margin: 0;
  display: flex;
  flex-direction: column;
}

@media (max-width: 768px) {
  .main-content {
    padding: 1rem;
  }
}

.url-shortener {
  background-color: white;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  margin-bottom: 2rem;
}

.input-group {
  display: flex;
  gap: 1rem;
  margin: 1rem 0;
}

.url-input {
  flex: 1;
  padding: 0.5rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 1rem;
}

.shorten-button {
  padding: 0.5rem 1rem;
  background-color: #2c3e50;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.shorten-button:hover {
  background-color: #34495e;
}

.result {
  margin-top: 1rem;
  padding: 1rem;
  background-color: #f8f9fa;
  border-radius: 4px;
}

.recent-urls {
  background-color: white;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.url-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.url-item {
  padding: 1rem;
  border-bottom: 1px solid #eee;
}

.url-item:last-child {
  border-bottom: none;
}

.url-info {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
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
  padding: 2rem;
}
</style>
