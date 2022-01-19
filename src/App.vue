<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <Header />
    <Main />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'
import Main from './components/Main.vue'



export default {
  name: 'App',
  components: {
    HelloWorld,
    Header,
    Main
  }
}
</script>

<style lang="scss">

</style>
