<script setup>
import { ref, computed } from 'vue'
const number = ref(5)
const squaredNumber = computed(() => {
  return number.value * number.value
})

const firstName = ref('Tuan')
const lastName = ref('Nguyen')
const fullName = computed(() => {
  return firstName.value + ' ' + lastName.value
})

const counter = ref(0)
const squredCounter = computed(() => {
  return counter.value * counter.value
})
const handleIncrement = () => {
  counter.value++
}
</script>

<template>
  <h1>Original Number: {{ number }}</h1>
  <h1>Squared Number: {{ squaredNumber }}</h1>

  <h1>Fullname is {{ fullName }}</h1>

  <h1>Counter {{ counter }}</h1>
  <h1>{{ squredCounter }}</h1>
  <button @click="handleIncrement">Increment</button>
</template>

<!-- Computed property này sẽ tự động cập nhật mỗi khi number thay đổi. -->
<!-- Trường hợp number thay đổi khi callback đó được kích hoạt -->
