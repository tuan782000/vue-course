<script setup>
import { ref } from 'vue'
import axios from 'axios'
const data = ref(null)
const fetchData = async () => {
  try {
    // Make a GET request using axios
    const response = await axios.get('https://jsonplaceholder.typicode.com/posts')
    // Handle the successfull response
    data.value = response.data
  } catch (error) {
    console.error(`Error Fetching data: ${error}`)
  }
}
</script>
<template>
  <h1>((Using Axios))</h1>
  <button @click="fetchData">Fetch Data</button>
  <div>
    <h2>Data from API:</h2>
    <pre>
        {{ data }}
    </pre>
  </div>
</template>
