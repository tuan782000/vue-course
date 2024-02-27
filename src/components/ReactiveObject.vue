<script setup>
import { reactive, watch } from 'vue'
const state = reactive({ username: 'alex' })

// Here we can't provide specific property of object
// - we have to provide the entire object, otherwise it's gonna give us error in the console.

// Ở đây chúng tôi không thể cung cấp thuộc tính cụ thể của đối tượng
// - chúng ta phải cung cấp toàn bộ đối tượng, nếu không nó sẽ báo lỗi cho chúng ta trong bảng điều khiển.
watch(state, (newVal, oldVal) => {
  // If we're using "object" both the new & the old values will be the same
  // Nếu chúng ta đang sử dụng "object" thì cả giá trị mới và cũ sẽ giống nhau
  console.log('new value', newVal)
  console.log('old value', oldVal)
})
</script>

<template>
  <h1>{{ state.username }}</h1>
  <button @click="state.username = 'jordan'">Change Name</button>
</template>