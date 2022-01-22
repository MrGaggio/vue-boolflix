<template>
  <div id="app">
    <Header />
    <!-- model per assegnare a una variabile un valore
     vuoto su cui girare il contenuto di inputText -->
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
    this.getFilms();
  },
  data() {
    return {
      //parte fissa della chiamata
      query: "https://api.themoviedb.org/3/search/",
      endpoint: 'movie?',
      api_key: "api_key=f0278b0dff056a07e75af2bb599a91bc",
      language: '&language=en-Us',
      ricerca: '&query=testo',
    };
  },
  methods: {
    getFilms() {
      // tutti i parametri necessari per effettuare la chiamata corretta, sono concatenati in modo da effettuare la chiamata come richiesto. es. chiamata corretta:

      axios(`${this.query}${this.endpoint}${this.api_key}${this.language}${this.ricerca}`)
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
