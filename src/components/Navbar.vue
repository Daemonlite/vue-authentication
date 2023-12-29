<template>
  <header class="bg-white shadow h-16 flex justify-between items-stretch">
    <router-link :to="{ name: 'home' }" class="inline-flex items-center px-5 h-full">
      Home
    </router-link>

    <div class="flex items-center">
      <router-link v-if="!user" :to="{ name: 'login' }" class="inline-flex items-center px-2 h-full transition-colors hover:bg-purple-100">
        Login
      </router-link>

      <router-link :to="{ name: 'login' }" v-else @click="logout" class="inline-flex items-center px-2 h-full transition-colors hover:bg-purple-100 cursor-pointer">
        Logout
      </router-link>
    </div>
  </header>
</template>


<script setup>
const user = JSON.parse(localStorage.getItem('userInfo'))

const logout = () => {
  localStorage.removeItem('userInfo')
}


</script>
