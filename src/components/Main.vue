<template>
  <dir>

  </dir>
</template>

<script>
// import axios from "axios"

export default {
  name: "Main",
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
