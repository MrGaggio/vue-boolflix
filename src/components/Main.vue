<template>
  <dir>
    <!-- passati tutti i dati dalla scheda Card.vue -->
    <Card v-for="(info, index) in cards" :key="index"
    :info="info"
    />
  </dir>
</template>

<script>
// import la scheda Card"
import Card from './Card.vue'
export default {
  name: "Main",
  components: {
    Card,
  },

  methods: {
    getPath(){
          this.locandine = this.result.data.results[this.index].poster_path
          console.log(this.locandine);
    }
  },
  /* passa da App.vue a Main.vue tramite le 'props' il contenuto dell'array cards.
  // per evitare warning l'array lo si passa in questo modo:

  nomeArray: {
    default () {
      return [];
    }
  } 
  Dopo si ripassa nell' App.vue e si aggancia il risultato nel <Main />
  */
  props: {
    cards: {
      default () {
        return [];
      },
    },
  },
}
</script>

<style></style>
