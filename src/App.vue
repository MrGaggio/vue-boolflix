<template>
  <div id="app">
    <!-- passato dall header con $emit e presa qui con $event. Inserita la funzione getFilm() e sotto gli ha dato il parametro text al posto del $event in questo modo legge il contenuto del textSearch -->
    <Header @search="getFilms($event)" />
    <Main />
    <Cards />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import Cards from "./components/Cards.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    Header,
    Main,
    Cards,
  },
  created() {
    //esegue la chiamata axios
    // this.getFilms();
  },
  data() {
    return {
      //parte fissa della chiamata
      query: "https://api.themoviedb.org/3/search/",
      endpoint: 'movie',
      api_key: "f0278b0dff056a07e75af2bb599a91bc",
      language: 'en-Us',
      searchText: '',
    };
  },
  methods: {
    getFilms(text) {
      this.searchText = text
      // tutti i parametri necessari per effettuare la chiamata corretta, sono concatenati in modo da effettuare la chiamata come richiesto.

      axios(`${this.query}${this.endpoint}?api_key=${this.api_key}&language=${this.language}&query=${this.searchText}`)
        .then((result) => {
          console.log(result);
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style lang="scss"></style>
