<script setup>
import { ref } from 'vue'

const user = ref({
  name: 'User Name',
  email: 'user@example.com',
  createdAt: new Date().toISOString()
})
</script>

<template>
  <div class="profile-container">
    <h1>Profile</h1>
    <div class="profile-card">
      <div class="profile-info">
        <div class="info-item">
          <label>Name:</label>
          <span>{{ user.name }}</span>
        </div>
        <div class="info-item">
          <label>Email:</label>
          <span>{{ user.email }}</span>
        </div>
        <div class="info-item">
          <label>Member Since:</label>
          <span>{{ new Date(user.createdAt).toLocaleDateString() }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.profile-container {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.profile-container h1 {
  color: #2c3e50;
  margin-bottom: 1rem;
}

.profile-card {
  background-color: white;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  width: 100%;
  max-width: 800px;
  margin: 0 auto;
}

.profile-info {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.info-item {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid #eee;
}

.info-item:last-child {
  border-bottom: none;
  padding-bottom: 0;
}

.info-item label {
  color: #7f8c8d;
  font-size: 0.9rem;
  font-weight: bold;
}

.info-item span {
  color: #2c3e50;
  font-size: 1.1rem;
}

@media (max-width: 768px) {
  .profile-card {
    padding: 1.5rem;
  }
}
</style> 