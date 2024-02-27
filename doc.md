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

### Interaction

V-for

The v-for directive is used to iterate over an array or an object and render a template for each item in the collection.

Lệnh v-for được sử dụng để lặp qua một mảng hoặc một đối tượng và hiển thị mẫu cho từng mục trong bộ sưu tập.

```vue
<script setup>
import { ref } from 'vue'
let peoples = ref(['alex', 'Jodarn', 'Nathan'])
</script>
<template>
  <p v-for="(person, index) in peoples" :key="index">{{ person }}</p>
</template>
```

index: này là optional có cũng được không có cũng được

Efficient DOM updates - Cập nhật DOM hiệu quả

When Vue renders a list of elements, it uses a virtual DOM to determine the most efficient way to update the actual DOM. The key helps Vue identify which elements have changed, have added, or been removed
Without keys, Vue may need to recreate the entire DOM structure for each update, Which can be less efficient.

Khi Vue hiển thị danh sách các thành phần, nó sử dụng DOM ảo để xác định cách hiệu quả nhất để cập nhật DOM thực tế. Key giúp Vue xác định phần tử nào đã thay đổi, đã thêm hoặc bị xóa
Nếu không có key, Vue có thể cần tạo lại toàn bộ cấu trúc DOM cho mỗi bản cập nhật, điều này có thể kém hiệu quả hơn.

Avoiding Common Pitfalls - Tránh những cạm bẫy phổ biến

Using key can help avoid common pitfalls, such as duplicate key warnings in the console or incorrect rendering when items are rearranged in the list.
Vue relies on keys to track the identity of elements, and using unique keys for each item ensures that Vue can accurately update the DOM based on changes in the list.

Việc sử dụng key có thể giúp tránh những lỗi thường gặp, chẳng hạn như cảnh báo key trùng lặp trong bảng điều khiển hoặc hiển thị không chính xác khi các mục được sắp xếp lại trong danh sách.
Vue dựa vào các key để theo dõi danh tính của các thành phần và việc sử dụng các key duy nhất cho từng mục đảm bảo rằng Vue có thể cập nhật chính xác DOM dựa trên những thay đổi trong danh sách.

### V-model

V-model is a directive provides two-way data binding on an input, textarea or select element. It creates a connection between the data in your component and input field, allowing changes in one to automatically update the other and vice versa.

V-model là một lệnh cung cấp liên kết dữ liệu hai chiều trên một phần tử đầu vào, vùng văn bản hoặc phần chọn. Nó tạo ra kết nối giữa dữ liệu trong trường thành phần và trường đầu vào của bạn, cho phép các thay đổi trong một dữ liệu này sẽ tự động cập nhật dữ liệu kia và ngược lại.

Two way binding?

Two way binding means that changes in your code automatically update what you see on the screen, and vice versa. It's like a live connection between your data and the user interface, making it easy to keep them in sync without writing alot of extra code.

Liên kết hai chiều có nghĩa là những thay đổi trong mã của bạn sẽ tự động cập nhật những gì bạn nhìn thấy trên màn hình và ngược lại. Nó giống như một kết nối trực tiếp giữa dữ liệu của bạn và giao diện người dùng, giúp bạn dễ dàng đồng bộ hóa chúng mà không cần phải viết thêm nhiều mã.

### Props

"Props" (short for properties) are a way to pass data from a parent component to a child component Props allow you to communicate between components by allowing them parent component to pass data down to its child components. This is useful for creating reusable and modular components.

"Props" (viết tắt của thuộc tính) là một cách truyền dữ liệu từ thành phần cha mẹ sang thành phần con Props cho phép bạn giao tiếp giữa các thành phần bằng cách cho phép thành phần cha mẹ truyền dữ liệu xuống thành phần con của nó. Điều này rất hữu ích cho việc tạo các thành phần mô-đun và có thể tái sử dụng.

### ComponentEvent

Component events are a way for child components to communicate with their parent components. They allow child components to
emit events (custom events) that can be listened to and handled by their parent components.

Các sự kiện của thành phần là một cách để các thành phần con giao tiếp với các thành phần cha của chúng. Chúng cho phép các thành phần con phát ra các sự kiện (sự kiện tùy chỉnh) có thể được các thành phần chính của chúng lắng nghe và xử lý.

Child Component emits an Event - Thành phần con phát ra một sự kiện

Inside a child component, you can use the $emit method to trigger a custom event. This event can carry data that you want to send to the parent.

Bên trong thành phần con, bạn có thể sử dụng phương thức $emit để kích hoạt sự kiện tùy chỉnh. Sự kiện này có thể mang dữ liệu mà bạn muốn gửi cho phụ huynh.

Parent Component Listens to the Event - Thành phần cha-mej lắng nghe sự kiện.

In the parent component's template, you can use the v-on directive (or the shorthand @) to listen for the custom event emitted by the child.

Trong mẫu của thành phần cha, bạn có thể sử dụng lệnh v-on (hoặc tốc ký @) để lắng nghe sự kiện tùy chỉnh do thành phần con phát ra.

Thành phần cha:

```vue
<script setup>
import FormComponent from './components/FormComponent.vue'

const formHandler = (username, email, password) => {
  console.log('username', username)
  console.log('email', email)
  console.log('password', password)
}
</script>
<template>
  <FormComponent @userInfo="formHandler" />
</template>
```

Thành phần con:

```vue
<script setup>
import { ref } from 'vue'
const username = ref('')
const email = ref('')
const password = ref('')
</script>
<template>
  <form @submit.prevent="$emit('userInfo', username, email, password)">
    <input type="text" placeholder="Enter your username" v-model="username" />
    <input type="email" placeholder="Enter your email" v-model="email" />
    <input type="password" placeholder="Enter your password" v-model="password" />
    <button>Submit</button>
  </form>
</template>
```

Khi thành phần con, có form thằng này sẽ phát sự kiện lên thằng cha bằng $emit, mình đặt tên cho sự kiện nó là userInfo. truyền các giá trị username, email, và password lên cấp cha.

Các trường input của biểu mẫu sử dụng v-model để liên kết với các biến được định nghĩa trong ref. Điều này giúp đồng bộ dữ liệu giữa giao diện người dùng và trạng thái của component.

### Slots

A Slot is like a space in a component where you can put different things. It allow you to create resuable components that can accept different content while maintaining a consistent structure.

Slot giống như một khoảng trống trong một thành phần nơi bạn có thể đặt những thứ khác nhau. Nó cho phép bạn tạo các thành phần có thể sử dụng được, có thể chấp nhận các nội dung khác nhau trong khi vẫn duy trì cấu trúc nhất quán.

Fallback/Default Content

Fallback content in slots refers to the default content that is displayed when no content is provided for a particular slot. It's a way to ensure that a component still has meaningful content, event if parent component does not pass any content a specific slot.

Nội dung dự phòng trong các vị trí đề cập đến nội dung mặc định được hiển thị khi không có nội dung nào được cung cấp cho một vị trí cụ thể. Đó là một cách để đảm bảo rằng một thành phần vẫn có nội dung có ý nghĩa, ngay cả khi thành phần cha mẹ không chuyển bất kỳ nội dung nào vào một vị trí cụ thể.

Named Slots:

A named slot is a way to assign a specific name a slot in a component. Unlike the default slot, which is unnamed and used when to explicit name is provided, name slots allow you to have multiple slots in a component and specify where the content should be inserted based on the slot's name.

Vị trí được đặt tên là một cách để gán một tên cụ thể cho một vị trí trong một thành phần. Không giống như vị trí mặc định, không được đặt tên và được sử dụng khi cung cấp tên rõ ràng, vị trí tên cho phép bạn có nhiều vị trí trong một thành phần và chỉ định vị trí nên chèn nội dung dựa trên tên của vị trí.

### Provide && Inject

Provide && Inject

The Provide and inject options are used for providing and injecting properties or data down the component hierarchy. They anable form of dependencies injection, allowing a parent component to provide data or methods that child components can then inject and use.

Các tùy chọn Cung cấp và đưa vào được sử dụng để cung cấp và đưa các thuộc tính hoặc dữ liệu vào hệ thống phân cấp thành phần. Chúng có thể thực hiện hình thức chèn phần phụ thuộc, cho phép thành phần cha mẹ cung cấp dữ liệu hoặc phương thức mà các thành phần con sau đó có thể đưa vào và sử dụng.

Provide - nhà cung cấp

Provide is an option in a parent component that allows it to share data or methods with its child components. It makes properties or methods available for injection into child components.

Cung cấp (Provide) là một tùy chọn trong thành phần gốc cho phép nó chia sẻ dữ liệu hoặc phương thức với các thành phần con của nó. Nó làm cho các thuộc tính hoặc phương thức có sẵn để đưa vào các thành phần con.

Inject - tiêm

Inject is an option in a child component that specifies which properties or methods it wants to recieve from its parent component. It allows a component to inject and use provided data or methods.

Tiêm (Inject) là một tùy chọn trong thành phần con chỉ định các thuộc tính hoặc phương thức mà nó muốn nhận từ thành phần cha của nó. Nó cho phép một thành phần chèn và sử dụng dữ liệu hoặc phương thức được cung cấp (Provide).

Tạo nhà cung cấp - Thằng muốn truyền gửi dữ liệu đi thì provide

Thằng cần nhận dữ liệu dùng Inject

Giải thích nhà cung cấp:

```js
// cha
// Using Provide With Array
provide('friends', ['Alex', 'Jordan', 'HuXn', 'John']) // tham số thứ 1 tên đại diện, tham số thứ 2 sẽ là dữ liệu truyền đi

// con
inject('friends') // lấy tên của nhà cũng cấp để sử dụng
```

```vue
<!-- Ông -->

<script setup>
import { provide } from 'vue'
provide('studentArrays', ['Tuan', 'Nguyen', 'Thai'])
</script>
<template>...</template>
```

<!-- cha, dùng con là cháu của ông ở cha, sau đó dùng cha ở ông vẫn có dữ liệu bình thường -->

...

<!-- cháu -->

<script setup>
import { inject } from 'vue'
const studentArrays = inject(studentArrays)
</script>
<template>
<ul>
  <li v-for="(student, index) in studentArrays" :key="index">
    {{ student }}
  </li>
</ul>
</template>
```


### Watchers

### Template Ref

### Async Components

### Composables

### Custom Directives

### Dynamic Components

### Data Fetching in Vue
