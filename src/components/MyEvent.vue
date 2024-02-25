<script setup>
import { ref } from 'vue'
// Tạo một đối tượng ref với giá trị mặc định là 0
let count = ref(0)

const incrementCounter = () => {
  count.value++
}

const decrementCounter = () => {
  count.value--
}

const submitHandler = (e) => {
  e.preventDefault()
  alert('Submit form success')
}

const showMessage = (message) => {
  alert(message)
}
</script>
<template>
  <h1>Count: {{ count }}</h1>
  <!-- <button v-on:click="count++">Increment</button> -->
  <!-- <button @:click="count++">Increment</button> -->
  <!-- @ === v-on -->
  <!-- <button @:click="count--">Decrement</button> -->

  <!-- Cách 2 tryền gọi hàm vào click -->
  <button v-on:click="incrementCounter">Increment</button>
  <button v-on:click="decrementCounter">Decrement</button>

  <form @:submit="submitHandler">
    <input type="text" placeholder="Please enter your name" />
    <input type="email" placeholder="Please enter your email" />
    <button type="submit">Submit</button>
  </form>

  <button @click="showMessage('This is message')">Show message</button>
</template>
<style></style>
