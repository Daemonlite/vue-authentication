<script setup>
import { ref } from 'vue'
import { useJwt } from '@vueuse/integrations/useJwt'

const token = JSON.parse(localStorage.getItem('userInfo')).access_token
const encodedJwt = ref(token)
const { header, payload } = useJwt(encodedJwt)
</script>

<template>
  <div>
    <h2 v-if="loading">Loading...</h2>
    <h2 v-else-if="error">Error: {{ error.message }}</h2>
    <h2 v-else>Welcome  {{ payload.username }}</h2>
  </div>
</template>


