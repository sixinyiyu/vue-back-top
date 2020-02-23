<template>
  <div id="app">
    <div style="height: 100vh;;backgroundColor: red;opacity: 0.5;">666</div>

    <div style="height: 300vh;backgroundColor: pink;opacity: 0.5;">sixsixsix</div>

    <div style="height: 200vh;backgroundColor: yellow;opacity: 0.5;">9999</div>
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <BackTop/>
  </div>
</template>

<script>
import BackTop from './components/BackTop.vue'

export default {
  name: 'App',
  components: {
    BackTop
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
