<template>
  <h2 class="g-1">Another global style</h2>
  <h2 class="l-1">Another local style</h2>
</template>

<!-- Global styling -->
<style>
.g-1 {
  background: fuchsia;
  color: white;
}
</style>
<!-- Local styling -->
<style scoped>
.l-1 {
  background: yellow;
  color: white;
}
</style>
