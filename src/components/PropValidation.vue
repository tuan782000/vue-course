<script setup>
// Basic
// const PropInfo = defineProps({ fullName: String, age: Number })
// Complex Props Validations
const props = defineProps({
  fullName: {
    type: String,
    required: true,
    default: 'Anonymous'
  },
  age: {
    type: Number,
    required: false // nếu false bỏ luôn cũng được tại mặc định false sẵn
  }
})
</script>
<template>
  <h1>Infomation</h1>
  <p>{{ props.fullName }}</p>
  <p>{{ props.age }}</p>
</template>
