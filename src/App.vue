<template>
  <div id="app">
    <Header 
    @search="searchFilm"/>
    <!-- model per assegnare a una variabile un valore
     vuoto su cui girare il contenuto di inputText -->
    <Main 
      :msg="messaggio"
    />
    <Cards />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import Cards from './components/Cards.vue'



export default {
  name: 'App',
  components: {
    Header,
    Main,
    Cards
  },
  data(){
    return {
      messaggio: ""
    }
  },
  methods: {
    //prende inputText dall'Header e lo passa all'App tramite $emit('search', inputText)"
    searchFilm (searchTxt) {
      this.messaggio = searchTxt;
    }
  }
}
</script>

<style lang="scss">

</style>
