<script setup>
const props = defineProps(['firstname', 'lastname'])
</script>
<template>
  <h1>{{ props.firstname }}</h1>
  <h1>{{ props.lastname }}</h1>
</template>
