<script setup>
const userInfo = JSON.parse(localStorage.getItem('userInfo'));

</script>

<template>
Welcome {{ userInfo }}
</template>

