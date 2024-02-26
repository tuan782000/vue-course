<script setup>
import { ref } from 'vue'
const username = ref('')
const email = ref('')
const password = ref('')
</script>
<template>
  <form @submit.prevent="$emit('userInfo', username, email, password)">
    <input type="text" placeholder="Enter your username" v-model="username" />
    <input type="email" placeholder="Enter your email" v-model="email" />
    <input type="password" placeholder="Enter your password" v-model="password" />
    <button>Submit</button>
  </form>
</template>
