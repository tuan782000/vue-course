<script setup>
import { ref } from 'vue'
import DynamicPropsComponent from './DynamicPropsComponent.vue'
import ChangingPropsValue from './ChangingPropsValue.vue'
import PropValidation from './PropValidation.vue'
import ComplexProps from './ComplexProps.vue'
import CustomValidator from './CustomValidator.vue'
const props = defineProps(['name'])

const firstname = ref('Tuan')
const lastname = ref('Nguyen')
const myFavoriteNumber = ref(7)
</script>

<template>
  <h1>{{ props.name }}</h1>
  <hr />
  <!-- v-bind viết tắt thành ":" -->
  <DynamicPropsComponent :firstname="firstname" :lastname="lastname" />
  <hr />
  <ChangingPropsValue :myFavoriteNumber="myFavoriteNumber" />
  <hr />
  <PropValidation :fullName="'Tuan Nguyen Thai'" :age="24" />
  <hr />
  <ComplexProps
    :friends="['alex', 'john', 'jodan', 'tom']"
    :userInfo="{ name: 'alex', age: 20, location: ['Earth', 'IDK'] }"
  />
  <hr />
  <CustomValidator name="Tuan" :age="20" password="impossiblePassword" />
</template>
