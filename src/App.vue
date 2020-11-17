<template>
  <div id="app">
    <h1>Currency Converter</h1>
    <div class="line">
      <Converter cur-a="USD" cur-b="BRL" />
      <Converter cur-a="BRL" cur-b="USD" />
    </div>
    
    <div class="line">
      <Converter cur-a="EUR" cur-b="BRL" />
      <Converter cur-a="BRL" cur-b="EUR" />
    </div>
  </div>
</template>

<script>

import Converter from "./components/Converter.vue"

export default {
  name: 'App',
  components: {
    Converter
  }
}
</script>

<style>
#app {
  margin: auto;
  max-width: 700px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.line{
  margin-top: 40px;
  display: flex;
  justify-content: space-around;
}
</style>
