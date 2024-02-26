<script setup>
import { ref } from 'vue'
const formData = ref({ username: '', email: '', password: '' })
const handleSubmit = (e) => {
  e.preventDefault()
  alert('Form submited')
}
</script>
<template>
  <form @submit="handleSubmit" autocomplete="off">
    <input type="text" placeholder="Please enter your name" v-model="formData.username" />
    <input type="email" placeholder="Please enter your email" v-model="formData.email" />
    <input type="password" placeholder="Please enter your name" v-model="formData.password" />
    <button type="submit">Submit</button>
  </form>

  <h1>{{ formData.username }}</h1>
  <h1>{{ formData.email }}</h1>
  <h1>{{ formData.password }}</h1>
</template>
