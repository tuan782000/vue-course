<script setup>
import { ref } from 'vue'
let peoples = ref(['Tuan', 'Nguyen', 'Thai'])

const books = ref([
  {
    id: 1,
    title: 'Tôi thấy hoa vàng trên cỏ xanh',
    author: 'Nguyễn Nhật Ánh',
    genre: 'Hư cấu',
    publicationYear: 2010
  },
  {
    id: 2,
    title: 'Dế Mèn phiêu lưu ký',
    author: 'Tô Hoài',
    genre: 'Hư cấu',
    publicationYear: 1941
  },
  {
    id: 3,
    title: 'ông lão đánh cá và biển cả',
    author: 'Ernest Hemingway',
    genre: 'Tiểu thuyết',
    publicationYear: 1952
  }
])

const movies = ref([
  ['Spiderman', 'Spiderman-2', 'Spiderman-3', 'Amazing Spiderman', 'Amazing Spiderman-2'],
  [
    'Tân tinh võ môn',
    'Quốc sản 007',
    'Đội bóng thiếu lâm',
    'Trường học Uy Long',
    'Tây du ngoại truyện',
    'Đỗ Thánh'
  ],
  ['Anh Hùng Xạ điêu', 'Thiên Long Bát Bộ', 'Ỷ thiên đồ Long Ký', 'Thần điêu hiệp lữ '],
  ['Nhà bà Nữ', 'Mai', 'Chị chị em em', 'Mắt biếc']
])

const games = ref({
  id: 1,
  title: 'Epic Adventure Game',
  genre: ['Action', 'Adventure', 'RPG'],
  platform: ['PC', 'Playbox', 'Xbox', 'Nitendo Switch'],
  releaseDate: '2022-03-15',
  developers: { name: 'Awesome Game Studio', location: 'San Francisco, CA', teamSize: 50 },
  ratings: { metacritic: 90, user: 4.8 },
  features: { singlePayer: true, multiPayer: true, onlineCoop: true, splitScreen: false },
  systemRequirements: {
    minimum: {
      os: 'Windows 10',
      process: 'Intel Core i5',
      memory: '8 GB RAM',
      graphics: 'NVIDA GTX 970',
      storage: '50 GB available space'
    }
  },
  recomended: {
    os: 'Windows 11',
    processor: 'Intel Core i7',
    memory: '16 GB RAM',
    graphics: 'NVIDA RTX 3080',
    storage: '100 GB available space'
  },
  storyLine: 'Embark on a thrilling adventure to save the world from impding doom!',
  characters: ['Hero', 'Sidekick', 'Villian', 'NPCs'],
  achivemnts: [
    { id: 1, name: 'Master Explore', description: 'Explore every corner of the game of the world' }
  ]
})

const complexObj = ref({
  game1: {
    title: 'Space Explorer',
    game: 'Sci-Fi',
    platform: 'PC',
    releaseDate: '2023-05-20'
  },
  game2: {
    title: 'Fantacy Quest',
    game: 'Fantacy',
    platform: 'Playstation',
    releaseDate: '2023-07-10'
  },
  book1: {
    title: 'Dune',
    author: 'Frank Herbert',
    genre: 'Science Fiction',
    publicationYear: 1965
  },
  book2: {
    title: 'To kill a Mockingbird',
    author: 'Happer Lee',
    genre: 'Fiction',
    publicationYear: 1960
  },
  move1: {
    title: 'Inception',
    director: 'Chirstoper Nolan',
    genre: 'Sci-Fi',
    relaseDate: '2010-07-16'
  },
  move2: {
    title: 'The Shawshank Red',
    director: 'Frank Dra',
    genre: 'Drama',
    relaseDate: '1994-09-23'
  }
})
</script>

<template>
  <!-- <h1>V-for</h1> -->
  <p v-for="(person, index) in peoples" :key="index">{{ index + 1 }}. {{ person }}</p>

  <h1>List of books:</h1>
  <ul v-for="book in books" :key="book.id">
    <li>
      Title: {{ book.title }}, author: {{ book.author }}, genre: {{ book.genre }}, public:
      {{ book.publicationYear }}
    </li>
  </ul>

  <!-- Mình có thể sử dụng cú pháp destructuring -->
  <h1>List of books with syntax Destructuring:</h1>
  <div v-for="{ id, title, author, genre, publicationYear } in books" :key="id">
    <p>Id: {{ id }}</p>
    <p>Title: {{ title }}</p>
    <p>Author: {{ author }}</p>
    <p>Genre: {{ genre }}</p>
    <p>Public: {{ publicationYear }}</p>
    <br />
  </div>

  <h1>List of movies:</h1>
  <div v-for="(movie, index) in movies" :key="index">
    <p v-for="(m, index) in movie" :key="index">{{ index + 1 }}. {{ m }}</p>
    <br />
  </div>

  <h1>List of information Game:</h1>
  <ul v-for="(value, key, index) in games" :key="index">
    {{
      index
    }}
    -
    {{
      key
    }}
    -
    {{
      value
    }}
  </ul>

  <h1>List of Mix:</h1>
  <ul v-for="(game, index) in complexObj" :key="index">
    <!-- Getting All Objects -->
    <li>{{ game }}</li>
    <br />

    <!-- Getting Single Value From Object -->
    <li v-for="(property, i) in game" :key="i">
      {{ property }}
    </li>
  </ul>
</template>
