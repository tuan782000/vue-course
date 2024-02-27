<script setup>
import {
  ref,
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted
} from 'vue'
// Đây là cú pháp sử dụng Composition API để import các hàm và biến từ Vue.js. Các hàm này là các Lifecycle Hooks và biến ref được sử dụng để tạo ra một biến có thể reactivity.

const message = ref('Hello, Vue!')
const isComponentMounted = ref(true)

// Biến message được tạo với ref để làm cho nó trở thành một biến có khả năng reactivity. isComponentMounted là một biến khác để theo dõi trạng thái hiện tại của việc gắn component vào DOM.

// Lifecycle hooks
onBeforeMount(() => {
  console.log('Component is about to be mounted')
})

onMounted(() => {
  console.log('Component has been mounted')
})

onBeforeUpdate(() => {
  console.log('Component is about to update')
})

onUpdated(() => {
  console.log('Component has been updated')
})

onBeforeUnmount(() => {
  console.log('Component is about to be unmounted')
})

onUnmounted(() => {
  console.log('Component has been unmounted')
})

// Các hàm này được gọi tại các giai đoạn khác nhau trong vòng đời của component, và chúng in ra các thông báo trạng thái tương ứng vào console.

const updateMessage = () => {
  message.value = 'Updated Message!'
}

const unmountComponent = () => {
  // Update the reactive variable to conditionally render the unmounted message
  isComponentMounted.value = false
}

//updateMessage là một hàm để cập nhật giá trị của message. unmountComponent là một hàm để gán giá trị false cho isComponentMounted, điều này sẽ làm cho phần template hiển thị thông báo "Component has been unmounted".
</script>

<template>
    <!-- Template sử dụng v-if để điều khiển việc hiển thị của phần component. Nếu isComponentMounted là true, nội dung của component sẽ được hiển thị, ngược lại, nếu isComponentMounted là false, thông báo "Component has been unmounted" sẽ được hiển thị. -->
  <div v-if="isComponentMounted">
    <p>{{ message }}</p>
    <button @click="updateMessage">Update Message</button>
    <button @click="unmountComponent">Unmount Component</button>
  </div>
  <div v-else>
    <p>Component has been unmounted</p>
  </div>
</template>
