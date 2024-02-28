<script setup>
import { ref, defineAsyncComponent } from 'vue'
const RenderFriends = defineAsyncComponent(() => import('./RenderFriends.vue'))

let showFriends = ref(false)

const toggleFriendList = () => (showFriends.value = !showFriends.value)
</script>

<template>
  <button @click="toggleFriendList">Toggle Friend List</button>
  <div v-if="showFriends">
    <RenderFriends />
  </div>
</template>
