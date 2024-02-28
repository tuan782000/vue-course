<script setup>
import { ref } from 'vue'

const count = ref(10)
const increment = () => count.value++
const decrement = () => count.value--

// When using the <script setup>
// - It's private by default
// - A parent referencing a child won't be able to access anything.

// First we have to expose all the properties and methods
// then we'd be able to use them in parent component.
//  - use use (defineExpose) to expose our data for the parent to use.

// Khi sử dụng <script setup>
// - Theo mặc định nó là riêng tư
// - Cha mẹ tham chiếu đến đứa trẻ sẽ không thể truy cập bất cứ thứ gì.

// Đầu tiên chúng ta phải hiển thị tất cả các thuộc tính và phương thức
// thì chúng ta có thể sử dụng chúng trong thành phần chính.
// - sử dụng use (defineExpose) để hiển thị dữ liệu của chúng tôi cho phụ huynh sử dụng.
defineExpose({ count, increment, decrement })
</script>

<template>
  <h3>Count: {{ count }}</h3>
  <button @click="increment">+</button>
  <button @click="decrement">-</button>
</template>
