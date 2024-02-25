<!-- eslint-disable no-unused-vars -->
<script setup>
// phục vụ cho content
const myMessages = 'Happy New Year'
const year = 2024
const add = (x, y) => {
  return x + y
}

// phục vụ cho attributes của thẻ
const google = 'https://www.google.com'
const amazingImage =
  'https://images.unsplash.com/photo-1708718904342-b6b5e7cb6c27?q=80&w=1887&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D'
const altImg = 'This is random Image'

const imgWidth = 200
const imgHeight = 200

// Đóng gói tất cả các biến trên thành 1 object

// Dynamic Binding
const imageInfo = {
  src: 'https://images.unsplash.com/photo-1707920857192-fda3d1f31cf7?q=80&w=1887&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
  alt: 'Another picture',
  width: 400,
  height: 400
}
</script>

<template>
  <h1>{{ myMessages + ' ' + year }}</h1>
  <!-- Có thể thực hiện tính toán -->
  <p>2 + 2 = {{ 2 + 2 }}</p>

  <p>Add: {{ add(5, 5) }}</p>

  <!-- <a v-bind:href="google">Visit Google</a> -->
  <a :href="google">Visit Google</a>

  <!-- <img v-bind:src="amazingImage" v-bind:alt="altImg"> -->
  <img :src="amazingImage" :alt="altImg" :width="imgWidth" :height="imgHeight" />

  <!-- Gọn hơn: thể hiện image thông qua object -->
  <!-- <img v-bind:="imageInfo" /> -->
  <img :="imageInfo" />
</template>

<style scope></style>
