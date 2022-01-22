<template>
  <dir>
    <!-- passati tutti i dati dalla scheda Card.ve -->
    <Card v-for="(prova1, index) in cards" :key="index"
    :info="prova1"
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
