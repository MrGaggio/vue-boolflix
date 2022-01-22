<template>
  <div id="app">
    <!-- passato dall header con $emit e presa qui con $event. Inserita la funzione getFilm() e sotto gli ha dato il parametro text al posto del $event in questo modo legge il contenuto del textSearch
    
    Per evitare di fare una doppia chiamata nel momento in cui andranno cercate anche le serieTV, si fa la chiamata alla funzione search() che include al suo interno anche la funzione getFiml() per la ricerca dei film, il valore dell $emit in questo caso va passato alla funzione search(), che diventa quindi search(text)
... (text è il searchText)     -->
    <Header @searchTesto="search($event)" />

    <!-- con :cards è andato a prendere il contenuto dei props dell'array cards nel main e con =cards gli ha assegnato il valore, in questo modo sono linkati. -->
    <Main :cards="cards" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    Header,
    Main
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
      textText: '',
      //cards è l'array vuoto che contiene il risultato della chiamata axios
      cards: [],
    };
  },
  methods: {
    search(text){
      this.textText = text
      this.getFilms()
    },
    getFilms() {
      // tutti i parametri necessari per effettuare la chiamata corretta, sono concatenati in modo da effettuare la chiamata come richiesto.

      axios(`${this.query}${this.endpoint}?api_key=${this.api_key}&language=${this.language}&query=${this.textText}`)
        .then((result) => {
          // dentro a (result).data.results si trovano i risultati della ricerca search(text)
          this.cards = result.data.results
          console.log(this.cards);
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
