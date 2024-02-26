<script setup>
// import MyComponents from './components/MyComponents.vue'
// import GlobalStyleVue from './components/GlobalStyle.vue'
// import LocalStyle from './components/LocalStyle.vue'
// import CombinedStyle from './components/CombinedStyle.vue'
// import ModuleStyle from './components/ModuleStyle.vue'
// import MyEvent from './components/MyEvent.vue'

// import MyReactiveComponent from './components/MyReactiveComponent.vue';
// import MyRefComponent from './components/MyRefComponent.vue';
// import MyRefandReactive from './components/MyRefandReactive.vue';
// import ComputedProperties from './components/ComputedProperties.vue'
// import ConditionalRendering from './components/ConditionalRendering.vue'
// import InteractionComponent from './components/InteractionComponent.vue';
// import InteractionWithModelComponent from './components/InteractionWithModel.vue'

// Props
import StaticPropsComponents from './components/StaticPropsComponents.vue'
import CustomValidator from './components/CustomValidator.vue'
</script>
<template>
  <!-- vbind và dynamic binding -->
  <!-- <MyComponents /> -->

  <!-- Css -->
  <!-- <GlobalStyleVue />
  <LocalStyle />
  <CombinedStyle />
  <ModuleStyle /> -->

  <!-- Event -->
  <!-- <MyEvent /> -->

  <!-- Reactive -->
  <!-- <MyReactiveComponent /> -->

  <!-- Ref -->
  <!-- <MyRefComponent /> -->

  <!-- Ref and Reactive -->
  <!-- <MyRefandReactive /> -->

  <!-- <ComputedProperties /> -->

  <!-- ConditionalRendering -->
  <!-- <ConditionalRendering /> -->
  <!-- <InteractionWithModelComponent /> -->
  <StaticPropsComponents name="Tuan" />
  <CustomValidator name="randomPerson" :age="20" password="impossiblePassword" />
</template>
<style scoped></style>
