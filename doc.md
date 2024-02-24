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
import { createApp } from "vue";
import App from "./App.vue";

createApp(App).mount("#app");
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