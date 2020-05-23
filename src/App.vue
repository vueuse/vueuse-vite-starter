<template>
  <div id="app">
    <img src="./logo.svg" />
    <h1>Hello <a href='https://github.com/vuejs/vite' target='__blank'>Vite</a> and <a href='https://github.com/antfu/vueuse' target='__blank'>VueUse</a>!</h1>

    <h3>Mouse: {{x}} x {{y}}</h3>
    <h3>
      Counter: {{count}}
      <a @click='inc()' style='margin-right:10px'>+</a>
      <a @click='dec()'>-</a>
    </h3>

    <br/><br/>
    <p><a href='https://github.com/antfu/vite-vueuse-starter' target='__blank'>Source</a></p>
    <p><a href='https://vueuse-next-example.netlify.app/' target='__blank'>Webpack Example</a></p>
  </div>
</template>

<script>
import { ref } from 'vue'
import { useMouse, useCounter } from '@vueuse/core'

export default {
  setup() {
    const { x, y } = useMouse()
    const { count, inc, dec } = useCounter()

    return {
      x, 
      y,
      count,
      inc,
      dec,
    }
  }
}
</script>

<style scoped>
html, body, h1, h2, h3, p {
  font-family: 'Noto Serif', serif;
  user-select: none;
}

#app {
  text-align: center;
  color: rgba(0,0,0,0.4);
}
img {
  width: 500px;
}
a {
  color: #41b883;
  text-decoration: none;
  cursor: pointer;
}
</style>
