<script setup>
const props = defineProps(['myFavoriteNumber'])
</script>
<template>
    <p>Num: {{ props.myFavoriteNumber }}</p>
</template>
