<script setup>
const myMessages = 'Happy New Year'
const year = 2024
const add = (x, y) => {
  return x + y
}
</script>

<template>
  <h1>{{ myMessages + ' ' + year }}</h1>
  <!-- Có thể thực hiện tính toán -->
  <p>2 + 2 = {{ 2 + 2 }}</p>

  <p>Add: {{ add(5, 5) }}</p>
</template>

<style scope></style>
