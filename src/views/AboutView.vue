<template>
  <div class="about">
    <div>
      <h1>사용자 목록</h1>
      <ul v-if="users.length">
        <li v-for="user in users" :key="user.email">{{ user.name }} ({{ user.email }})</li>
      </ul>
      <p v-else>불러오는 중 또는 사용자가 없습니다.</p>
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue'
import axios from 'axios'

const users = ref([])

onMounted(async () => {
  try {
    const response = await axios.get('/api/users')
    users.value = response.data
  } catch (error) {
    console.error('❌ 사용자 정보 불러오기 실패:', error)
  }
})
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
  }
}
</style>
