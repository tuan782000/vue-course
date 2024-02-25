<template>
  <h1 class="text-red">Global Styling</h1>
  <p class="local">Trying local scope in this component</p>
</template>

<!-- Global Style -->
<!-- Vì mình ko đặt scoped cho style nên LocalStyle (con có thể bị ảnh hưởng) -->
<style>
    .text-red {
        color: red;
    }
</style>
<!-- Global Style: là viết css ngay trong file -->