<script setup>
import { ref, onMounted } from 'vue'
// dữ liệu ban đầu
const quotes = ref([
  {
    text: 'The only way to do great work is to love what you do.',
    author: 'Steve Jobs'
  },
  {
    text: "Believe you can and you're halfway there.",
    author: 'Theodore Roosevelt'
  },
  {
    text: "Life is what happens when you're busy making other plans.",
    author: 'John Lennon'
  }
])
// giá trị ban đầu 
const currentQuote = ref({ text: '', author: '' })
// Tính năng random
const getRandomQuote = () => {
  const randomIndex = Math.floor(Math.random() * quotes.value.length)
  currentQuote.value = quotes.value[randomIndex]
}

onMounted(getRandomQuote)
// onMounted(getRandomQuote) được sử dụng để gọi hàm getRandomQuote ngay sau khi component được mount lên. Điều này đảm bảo rằng khi trang web được tải lên, một câu trích dẫn ngẫu nhiên sẽ được hiển thị ngay lập tức mà không cần phải bấm nút kích hoạt sự kiện mà ta đã gán cho button. Và tất nhiên mỗi lần reload lại onMounted này sẽ được chạy lại

</script>
<template>
  <div class="quote-generator">
    <h1 class="app-title">Random quote Generator</h1>
    <blockquote class="quote-container">
      <p>{{ currentQuote.text }}</p>
      <cite>{{ currentQuote.author }}</cite>
    </blockquote>
    <button @click="getRandomQuote" class="quote-button">Get random Quote</button>
  </div>
</template>
<style scoped>
.quote-generator {
  max-width: 400px;
  margin: 50px auto;
  padding: 20px;
  text-align: center;
  border: 1px solid #ccc;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}
</style>

<!-- Lần đầu truy cập
Nạp dữ liệu cho quotes

Đặt giá trị ban đầu currentQuote text và author

onMounted

Các html bên dưới ban đầu sẽ là rỗng hết do giá trị currentQuote là rỗng

nút button là chức năng khi mà click vào gọi getRandomQuote 
-->