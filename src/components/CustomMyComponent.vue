<script setup>
// mình đã tạo ra được 1 v-directive, tác dụng thằng này là lấy ra được thẻ đó in ra ra cả nội dung trong console
const vFormateDiv = {
  mounted: (el, binding) => {
    console.log(el)
    console.log(binding)
    // el.style.fontSize = '4rem'
    el.style.fontStyle = 'Italic'
    el.style.color = 'teal'

    el.style.fontSize = `${binding.value}rem`
    el.style.border = `${binding.value}px solid teal`
  }
}

const vCustomDiv = {
  mounted: (el, binding) => {
    switch (binding.arg) {
      case 'orange':
        el.style.color = 'orange'
        break
      case 'pink':
        el.style.color = 'pink'
        break
      case 'purple':
        el.style.color = 'purple'
        break
      case 'teal':
        el.style.color = 'teal'
        break
      default:
        el.style.color = 'black'
    }
  }
}
</script>
<template>
  <div v-formate-div="4">Using simple custom directive</div>
  <div v-Custom-div:orange>Using simple custom directive</div>
  <div v-Custom-div:pink>Using simple custom directive</div>
  <div v-Custom-div:purple>Using simple custom directive</div>
  <div v-Custom-div:teal>Using simple custom directive</div>
</template>
