<script setup>
import { reactive } from 'vue'
// Lý do đặt let thay vì const vì nó thay đổi theo thời gian
let initialState = reactive({ count: 0 })

let initial = reactive({ val: { count: 0 }, user: ['Tuan', 'Nguyen', 'Tung'] })
const changeUser = () => {
  initial.user[0] = "Vien",
  initial.user[1] = "Vu"
}
</script>
<template>
  <h1>Count: {{ initialState.count }}</h1>
  <button @click="initialState.count++">+</button>
  <button @click="initialState.count--">-</button>

  <h1>Current Count: {{ initial.val.count }}</h1>
  <h2>Users: {{ initial.user }}</h2>

  <button @click="initial.val.count += 10">Increment 10</button>
  <button @click="changeUser">Change User</button>
</template>
