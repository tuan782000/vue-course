<script setup>
const props = defineProps({ friends: Array, userInfo: Object })
</script>
<template>
  <h1>{{ props.friends }}</h1>
  <h1>{{ props.userInfo }}</h1>
  <hr />
  <!-- Interating Over Friends Array -->
  <ul v-for="(friend, index) in friends" :key="index">
    <li>{{ friend }}</li>
  </ul>
  <hr />
  <ul v-for="(info, index) in userInfo" :key="index">
    <li>{{ info }}</li>
  </ul>
</template>
