<!-- HTML -->
<template>
  <h1>This is parent Component</h1>
  <p>
    Lorem ipsum dolor, sit amet consectetur adipisicing elit. Voluptates minima quo autem assumenda
    beatae quasi vel ratione veniam provident, exercitationem aperiam laborum. Rerum cumque natus
    doloremque delectus consequuntur numquam tempora?
  </p>
  <AnotherComponent />
</template>
<!-- CSS -->
<style scoped></style>
<!-- JS -->
<script setup>
import AnotherComponent from './AnotherComponent.vue'
console.log('Hello World')
</script>
