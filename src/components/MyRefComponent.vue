<script setup>
import { ref } from 'vue'
let count = ref(0)

const handleIncrement = () => {
  count.value++
}

const handleDecrement = () => {
  count.value--
}

let username = ref('')
const handleAddUserName = () => {
  username.value = 'Tuan'
}

let userList = ref(['Tuan', 'Nguyen', 'Thai'])

const addListUser = () => {
  userList.value.push('Nhi')
}

let userInfo = ref({
  name: 'Tuan',
  age: 24,
  location: ['Quy Nhon city', 'Ho Chi Minh city'],
  isMarried: false
})

const handleChangeInfo = () => {
  userInfo.value.name = 'Nhi'
  userInfo.value.Age = 11
  userInfo.value.location[0] = 'Quy Nhon city'
  userInfo.value.location[1] = undefined
  userInfo.value.isMarried = false
}
</script>
<template>
  <h1>Count: {{ count }}</h1>
  <button @click="handleIncrement">increment</button>
  <button @click="handleDecrement">decrement</button>

  <h1>Username: {{ username }}</h1>
  <button @click="handleAddUserName">Add</button>

  <h1>User List: {{ userList }}</h1>
  <button @click="addListUser">Add List User</button>

  <h1>User Info</h1>
  <p>Name: {{ userInfo.name }}</p>
  <p>Age: {{ userInfo.age }}</p>
  <p>Location: {{ userInfo.location }}</p>
  <p>Married: {{ userInfo.isMarried ? 'Married' : 'is not Married' }}</p>

  <button @click="handleChangeInfo">Change Info</button>

</template>
