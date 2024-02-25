<script setup>
import { reactive, ref } from 'vue'
let friends = reactive([ref('Tuan'), ref('Huy'), ref('Dat'), ref('Tai')])
</script>
<template>
  <h1>1. {{ friends[0] }}</h1>
  <h1>2. {{ friends[1] }}</h1>
  <h1>3. {{ friends[2] }}</h1>
  <h1>4. {{ friends[3] }}</h1>

  <button @click="friends[0] = 'Tuấn'">Change Content postion 0</button>
</template>

<style></style>
