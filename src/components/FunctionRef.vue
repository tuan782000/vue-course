<script setup>
const myRefFunc = (el) => {
  console.log(el.textContent) // reading text content - đọc nội dung content
  el.textContent = 'Text Changed' // Changing Text Content - Thay đổi chữ
  el.style.color = 'red' // Changing Text Color - Thay đổi màu
}
</script>

<template>
  <h1 :ref="myRefFunc">This is initial value</h1>
</template>
