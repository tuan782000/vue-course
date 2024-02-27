<script setup>
import { ref, watch } from 'vue'
const message = ref('Hello, Vue!')

const inputText = ref('')

// Watch for changes in inputText and update message accordingly
// Theo dõi những thay đổi trong inputText và cập nhật thông báo tương ứng
watch(inputText, (newValue, oldValue) => {
  // You can perform some logic here when inputText changes
  // Bạn có thể thực hiện một số logic ở đây khi inputText thay đổi
  console.log(newValue)
  console.log(oldValue)
  message.value = `You typed: ${newValue}`
})
</script>

<template>
  <div>
    <h1>{{ message }}</h1>
    <input v-model="inputText" placeholder="Type something..." />
  </div>
</template>