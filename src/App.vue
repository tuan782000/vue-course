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
// import StaticPropsComponents from './components/StaticPropsComponents.vue'
// import CustomValidator from './components/CustomValidator.vue'

// Event Component
// import ComponentEvent from './components/ComponentEvent.vue'
// import FormComponent from './components/FormComponent.vue'
// import { ref } from 'vue'
// let count = ref(0)

// const formHandler = (username, email, password) => {
//   console.log('username', username)
//   console.log('email', email)
//   console.log('password', password)
// }

// Slots
// import SlotComponent from './components/SlotComponent.vue'
// import FallbackContent from './components/FallbackContent.vue'
// import NamedSlot from './components/NamedSlot.vue'

// Provide && Inject
// import { provide } from 'vue'
// import SchoolComponent from './components/SchoolComponent.vue'
// import PracticeComponent from './components/PracticeComponent.vue';

// provide('studentName', 'Alex')
// provide('studentAge', 20)
// provide('studentLocation', ['Earth', 'IDK'])

// // Using Provide With Array
// provide('friends', ['Alex', 'Jordan', 'HuXn', 'John'])

// // Using Provide With Object
// provide('games', {
//   id: 1,
//   title: 'Epic Adventure Game',
//   genre: ['Action', 'Adventure', 'RPG'],
//   platform: ['PC', 'PlayStation', 'Xbox', 'Nintendo Switch'],
//   releaseDate: '2022-03-15',
//   developer: {
//     name: 'Awesome Game Studios',
//     location: 'San Francisco, CA',
//     teamSize: 50
//   }
// })

// // Using Provide With Array Of Objects
// provide('moreGames', [
//   {
//     title: 'Space Explorer',
//     genre: 'Sci-Fi',
//     platform: 'PC',
//     releaseDate: '2023-05-20'
//   },
//   {
//     title: 'Fantasy Quest',
//     genre: 'Fantasy',
//     platform: 'PlayStation',
//     releaseDate: '2023-07-10'
//   },
//   {
//     title: 'Inception',
//     director: 'Christopher Nolan',
//     genre: 'Sci-Fi',
//     releaseDate: '2010-07-16'
//   },
//   {
//     title: 'The Shawshank Redemption',
//     director: 'Frank Darabont',
//     genre: 'Drama',
//     releaseDate: '1994-09-23'
//   }
// ])

// LifeCycle Hooks
// import LifeCycleHooks from './components/LifeCycleHooks.vue'

// Watch
// import BasicComponent from './components/BasicComponent.vue';
// import ReactiveObject from './components/ReactiveObject.vue';
// import UsingGetterFunction from './components/UsingGetterFunction.vue';
// import MultipleSources from './components/MultipleSources.vue'

// Refs
// import BasicRef from './components/BasicRef.vue'
// import FunctionRef from './components/FunctionRef.vue'

// Async
// import ToggleFriends from './components/ToggleFriends.vue'

// Composable
import CounterComponent from './components/CounterComponent.vue'
import Todolist from './components/Todolist.vue'
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

  <!-- Props -->
  <!-- <StaticPropsComponents name="Tuan" />
  <CustomValidator name="randomPerson" :age="20" password="impossiblePassword" /> -->

  <!-- Component event -->
  <!-- <h1>Count: {{ count }}</h1>
  <ComponentEvent @incrementCounter="count++" />
  <hr />
  <FormComponent @userInfo="formHandler" /> -->

  <!-- Slot -->
  <!-- <SlotComponent>
    <h1>Content 1</h1>
    <h2>Content 2</h2>
  </SlotComponent>
  <hr />
  <FallbackContent>
    <p>Fallback will not work because I'm providing content inside the component</p>
  </FallbackContent>
  <NamedSlot>
    <template v-slot:one>
      <h1>This content will go to slot "one"</h1>
    </template>

    <template #two>
      <h1>This content will go to slot "two"</h1>
    </template>
  </NamedSlot>

  <hr />

  <DefaultSlot>
    <template #default>
      <h1>This is some random default content</h1>
    </template>
  </DefaultSlot> -->

  <!-- Provide && Slot -->
  <!-- <SchoolComponent />
  <PracticeComponent /> -->

  <!-- <LifeCycleHooks /> -->

  <!-- <BasicComponent />
  <ReactiveObject />
  <UsingGetterFunction />
  <MultipleSources /> -->

  <!-- <BasicRef />
  <FunctionRef /> -->

  <!-- Async Component -->
  <!-- <ToggleFriends /> -->

  <CounterComponent />
  <Todolist />
</template>
<style scoped></style>
