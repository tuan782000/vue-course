<template>
  <h1 v-bind:class="$style['m-class']">Using Module Css with $ syntax(kabak-case)</h1>

  <h1 :class="$style.anotherClass">Hello</h1>
</template>

<style module>
/* kabak-case */
.m-class {
  background: firebrick;
  color: white;
}
.anotherClass {
  background: green;
  color: white;
}
</style>
