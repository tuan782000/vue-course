<script setup>
import { ref } from 'vue'
const isTrue = false
const isFalse = false

const isVisible = ref(true)
const handleToggle = () => {
  isVisible.value = !isVisible.value
}

const isActive = ref(true);
const handleTogglePost = () => {
  isActive.value = !isActive.value
}

const isUserLogin = ref(true)
const userName = 'Tuan'
const showDetails = ref(isUserLogin)


const loggedIn = ref(false)
const admin = 'admin'

const handleLogin = () => {
  loggedIn.value = !loggedIn.value
}

</script>
<template>
  <div>
    <p v-if="isTrue">This will show if isTrue is true.</p>
    <p v-else-if="isFalse">This is will show if isFalse is true.</p>
    <p v-else>This will show if neither isTrue nor isFalse is true.</p>
    <!-- 1 số lưu ý: v-if hoặc v-else-if có tồn tại thì sẽ hiện ở body, không tồn tại thì sẽ xóa khỏi phần body-->
    <!-- 
         Ở trên Nếu 1 đúng 2 sai hiện p số 1. 
         Nếu 1 sai 2 đúng hiện p số 2 
         Còn lại cả đều false hiện p số 3 -->

    <!-- v-show -->
    <p v-show="isVisible">This paragraph will be shown or hidden based on the value of isVisible</p>
    <button @click="handleToggle">Toggle Visibility</button>

    <h1 v-if="isUserLogin">Welcome, {{ userName }}</h1>
    <p v-else>Please login to access this content.</p>
    <div v-show="showDetails">
      <h4>You're now able to modify your dashboard</h4>
    </div>

    <div v-if="isActive">
      <h1>Blog</h1>
      <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Cumque officia nisi voluptas officiis, dolor impedit at quisquam modi laudantium harum in iure ipsum enim blanditiis eveniet voluptatem, ut expedita voluptatum.</p>
    </div>

    <button @click="handleTogglePost">Toggle Blog</button>

    <div v-if="loggedIn">
      Welcome, {{ admin }}
      <button @click="handleLogin">Logout</button>
    </div>
    <div v-else>
      <button @click="handleLogin">Loggin</button>
    </div>

  </div>
</template>
<style scoped></style>
