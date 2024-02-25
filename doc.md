# Học VUE

# VUE là gì?

VUEJS is a framework used for building user interfaces, particularly for single-page applications (SPAs). It is designed to be incrementally adaptable and can be easily integrated into other projects.

VUEJS là 1 framework sử dụng để xây dựng giao diện người dùng, cụ thể là ingle-page applications (SPAs). Nó được thiết kế để có thể thích ứng dần dần và có thể dễ dàng tích hợp vào các dự án khác.

## Setup Project:

npm create vue@latest

## Giải thích sơ về các thư mục

node_modules: nơi chứa các thư viện mình đã cài

public: nơi lưu trữ icon, hình ảnh chẳng hạn

src: chứa mã nguồn dự án, mình sẽ làm việc ở đây

.gitignore: chứa tên các file hoặc thư mục sẽ được loại bỏ ra trước khi đưa lên git

index.html: có đoạn chứa div có id là app, mọi thứ src được generate và bỏ vào đúng ngay vị trí đó.

jsconfig.json: cấu hình js cho dự án

package.json: các phiên bản thư viện đã cài đặt, setup các câu lệnh chạy dự án,...

App.vue

```js
import { createApp } from 'vue'
import App from './App.vue'

createApp(App).mount('#app')
```

lấy createApp từ thư viện vue
lấy App từ App.vue

Truyền App vào thư viện createApp, sau đó mount (phương thức này sẽ render) và đặt vao id app

### Component

What is component?

A component is an resuable and self-contained unit that encapsulates a specific piece of functionality or user interface. Components are a fundamental building block of Vue applications, and they allow you to organize and structure your code in a modular way.

Thành phần là một đơn vị độc lập và có thể sử dụng được, đóng gói một phần chức năng hoặc giao diện người dùng cụ thể. Thành phần là khối xây dựng cơ bản của ứng dụng Vue và chúng cho phép bạn sắp xếp và cấu trúc mã của mình theo cách mô-đun.

In Simple Terms

A component is like a building block for your website. Imageine it as a small, resuable part of your webpage that you can easily use in different places. It's like a lego blocks that you can use over again to build different things.

Một component giống như 1 khối cho web của bạn. Hãy hình dung nó như một phần nhỏ, có thể sử dụng lại được trên trang web của bạn mà bạn có thể dễ dàng sử dụng ở những nơi khác nhau. Nó giống như những khối Lego mà bạn có thể sử dụng lại để xây dựng những thứ khác nhau.

```js
// HelloWorld.vue
<template>
  <h1>This is parent Component</h1>
  <AnotherComponent />
</template>
```

```js
// AnotherComponent.vue
<template>
  <h1>--Nested Component</h1>
</template>
```

Cha HelloWorld.vue

Con AnotherComponent.vue

Ví dụ ở trên là con đang nằm trong thằng cha

Tóm lại: Cây gia phả

App.Vue
-- HelloWorld.vue
-- AnotherComponent.vue

### Text Interpolation {{ data }}

Text Interpolation is refers to the process of dynamically binding data to the content of an HTML element in your template. It allows you to display the value of a JavaScript expression or a variable within the markup.

Nội suy ví dụ: {{ code JavaScript ở đây }} văn bản đề cập đến quá trình liên kết động dữ liệu với nội dung của phần tử HTML trong mẫu của bạn. Nó cho phép bạn hiển thị giá trị của biểu thức JavaScript hoặc một biến trong phần đánh dấu.

```vue
<!-- Con -->
<script setup>
const myMessages = 'Happy New Year'
const year = 2024
const add = (x, y) => {
  return x + y
}
</script>

<template>
  <h1>{{ myMessages + ' ' + year }}</h1>
  <!-- Có thể thực hiện tính toán -->
  <p>2 + 2 = {{ 2 + 2 }}</p>
  <!-- 2 + 2 = 4 -->

  <p>Add: {{ add(5, 5) }}</p>
  <!--Add: 10 -->
</template>

<style scope></style>

<!-- Cha -->
<script setup>
import MyComponents from './components/MyComponents.vue'
</script>
<template>
  <MyComponents />
</template>
<style scoped></style>
```

### Attributes Bindings:

Attribute biding is way to bind HTML attributes to data in Vue instance.

- Cách cũ: v-bind:attr
- Cách mới: :attr

```vue
<a v-bind:href="google">Visit Google</a>

<!-- or -->

<a :href="google">Visit Google</a>
```

Phân tích 1 chút

```vue
<script setup>
const google = 'https://www.google.com'
</script>
<a href="google">Visit Google</a>
<a :href="google">Visit Google</a>
```

Không có 2 chấm ở trước thì href sẽ là google chỉ là tên bình thường

Nếu có 2 chấm trước nó sẽ hiểu là v-bind: google trong attributes sẽ là tên biến đã khai báo ở trên

### Style in Vue:

Có 4 cách Style

Global style: style css trong file đó luôn

Local style: style css thuộc cha của nó.

Module style

Combined style: kết hợp giữa local và global style

### Event handlers in Vue

"V-on" tương đương "@"" sau đó mình sẽ thêm sự kiện cho nó

```vue
<script>
import { ref } from 'vue'
// Tạo một đối tượng ref với giá trị mặc định là 0
let count = ref(0) // ref là đối tượng đại diện cho giá trị ban đầu
const incrementCounter = () => {
  count.value++
}

const decrementCounter = () => {
  count.value--
}
</script>

<h1>Count: {{ count }}</h1>
<button v-on:click="incrementCounter">Increment</button>
<button v-on:click="decrementCounter">Decrement</button>
```

### Reactivity in vue

Reactivity means that the framework can be automatically update UI when the information behind it changes. It is a core concept that allows you to create dynamic and responsive applications without manually manipulating the DOM.

Khả năng phản ứng có nghĩa là khung có thể tự động cập nhật giao diện người dùng khi thông tin đằng sau nó thay đổi. Đó là khái niệm cốt lõi cho phép bạn tạo các ứng dụng động và đáp ứng mà không cần thao tác DOM theo cách thủ công.

### Reactive

The reactive function is used to create reactive objects. A reactive object is an object where changes to it is properties
are automatically detected, triggering updates in the user interface. It is a way to make an object "reactive" in Vue.js

Hàm phản ứng được sử dụng để tạo các đối tượng phản ứng. Một đối tượng phản ứng là một đối tượng trong đó các thuộc tính của nó thay đổi được tự động phát hiện, kích hoạt cập nhật trong giao diện người dùng. Đó là một cách để tạo một đối tượng "phản ứng" trong Vue.js

Can't store primitive data types

Cách hoạt động của ref và reactive đều là các cách để quản lý và theo dõi trạng thái trong một component

Đối tượng trả về:

ref: Trả về một đối tượng ref với một thuộc tính .value để truy cập và cập nhật giá trị. Đối tượng này thường được sử dụng cho trạng thái đơn giản.
reactive: Trả về một đối tượng proxy hoàn toàn mới, mà bạn có thể truy cập và cập nhật trực tiếp các thuộc tính của nó. Đối tượng này thường được sử dụng cho trạng thái phức tạp hơn với nhiều thuộc tính.
Cách truy cập và cập nhật giá trị:

ref: Truy cập và cập nhật giá trị thông qua .value, như count.value.
reactive: Truy cập và cập nhật trực tiếp các thuộc tính, như user.name.
Áp dụng cho loại dữ liệu:

ref: Thích hợp cho trạng thái đơn giản, giữ một giá trị.
reactive: Thích hợp cho trạng thái phức tạp với nhiều thuộc tính, giống như một đối tượng.

### Ref

ref() is used to create a reactive reference to a value. Unlike the reactive function, which is used for creating reactive objects, ref is specifically designed for creating reactive single value.

You can store any value you want: Bạn có thể lưu trữ bất kỳ giá trị nào bạn muốn

### Computed Properties

A computed property is a special kind of variable that automatically updates itself whenever the data it depends on changes

It's like a little worker that watches certain data, performs some work on it, and always give you the most up-to-date result.

Thuộc tính "computed" là một loại biến đặc biệt tự động cập nhật bất cứ khi nào dữ liệu phụ thuộc vào thay đổi

Nó giống như một công nhân nhỏ theo dõi một số dữ liệu nhất định, thực hiện một số công việc trên đó và luôn cung cấp cho bạn kết quả cập nhật nhất.

### Conditional Rendering

Conditional Rendering is refers to the ability to conditionally display or hide elements in the user interface based on certain conditions or expressions.

Kết xuất có điều kiện đề cập đến khả năng hiển thị hoặc ẩn các thành phần trong giao diện người dùng có điều kiện dựa trên các điều kiện hoặc biểu thức nhất định.

v-if(condition)

v-else-if(condition)

v-else

v-show

- V-show directive is used for conditional rendering. It toggles the visibility of an element based on the truthiness of the provided expression. Unlike v-if, which completely adds or removes the element from the DOM, v-show toggles the css display property of the element to control its visibility while keeping it in the DOM.

- Lệnh V-show được sử dụng để hiển thị có điều kiện. Nó thay đổi mức độ hiển thị của một phần tử dựa trên tính xác thực của biểu thức được cung cấp. Không giống như v-if, bổ sung hoặc loại bỏ hoàn toàn phần tử khỏi DOM, v-show chuyển đổi thuộc tính hiển thị css của phần tử để kiểm soát khả năng hiển thị của nó trong khi vẫn giữ nó trong DOM.

```Vue
<script setup>
const isTrue = false
const isFalse = false
</script>
<template>
  <div>
    <p v-if="isTrue">This will show if isTrue is true.</p>
    <p v-else-if="isFalse">This is will show if isFalse is true.</p>
    <p v-else>This will show if neither isTrue nor isFalse is true.</p>
    <!-- 1 số lưu ý: v-if hoặc v-else-if có tồn tại thì sẽ hiện ở body, không tồn tại thì sẽ xóa khỏi phần body-->
    <!--
         Ở trên Nếu 1 đúng 2 sai hiện p số 1.
         Nếu 1 sai 2 đúng hiện p số 2
         Còn lại cả đều false hiện p số 3 -->
  </div>
</template>
<style scoped></style>
```

```vue
<script setup>
import { ref } from 'vue'
let visible = ref(true)

const handleToggle = () => {
  visible.value = !visible.value
}
</script>
<template>
  <!-- Tác dụng v-show chỉ ẩn nó đi không xóa nó khỏi body -->
  <!-- ẩn nó bằng cách bổ sung display:none -->
  <p v-show="visible">Hello</p>
  <!-- v-on:click -->
  <button @click="handleToggle">Toggle</button>
</template>
```
