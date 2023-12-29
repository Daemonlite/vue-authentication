<template>
  <header class="bg-white shadow h-16 flex justify-between items-stretch">
    <router-link :to="{ name: 'home' }" class="inline-flex items-center px-5 h-full">
      Home
    </router-link>

    <div class="flex items-center">
      <router-link :to="{ name: 'login' }" class="inline-flex items-center px-2 h-full transition-colors hover:bg-purple-100">
        Login
      </router-link>

      <router-link :to="{ name: 'login' }" @click="logout" class="inline-flex items-center px-2 h-full transition-colors hover:bg-purple-100 cursor-pointer">
        Logout
      </router-link>
    </div>
  </header>
</template>

<script setup>

const logout = () => {
  localStorage.removeItem('userInfo')
  alert('Logging out...');
}
</script>
