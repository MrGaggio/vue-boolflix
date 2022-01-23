<template>
  <!-- :info="card" passa il contenuto dell'oggetto-->
  <div class="cards">
    <h1>
      {{ (info.title) ? info.title : info.name }}
    </h1>
    <h2>
      {{ (info.original_title) ? info.original_title : info.original_name }}
    </h2>
    <div class="language">
        <!-- nel v-if verifica se original language è contenuto all'interno dell'array e lo stampa come immagine. Il require() è indispensabile per renderizzare il file png, senza non lo potrebbe caricare perchè non verrebbe incluso -->
      <img
        v-if="isAvailable"
        :src="require(`../assets/img/${info.original_language}.png`)"
        :alt="info.original_title"
      />
      <!-- invece se non è presente stampa normalmente senza bandiera (v-else) -->
      <h3 v-else>{{ info.original_language }}</h3>
      <p>
        {{ info.vote_average }}
      </p>
    </div>
  </div>
</template>

<script>
/*
Milestone 2:
Trasformiamo la stringa statica della lingua in una vera e propria bandiera della nazione corrispondente, gestendo il caso in cui non abbiamo la bandiera della nazione ritornata dall’API (le flag non ci sono in FontAwesome).

Allarghiamo poi la ricerca anche alle serie tv. Con la stessa azione di ricerca dovremo prendere sia i film che corrispondono alla query, sia le serie tv, stando attenti ad avere alla fine dei valori simili (le serie e i film hanno campi nel JSON di risposta diversi, simili ma non sempre identici)
Qui un esempio di chiamata per le serie tv:
https://api.themoviedb.org/3/search/tv?api _key=e99307154c6dfb0b4750f6603256716d&language=it_IT&query=scrubs
*/

export default {
  name: "Card",
  //anche per gli oggetti il default deve essere una funzione ma si puo non mettere
  props: {
    info: Object,
  },
    computed:{
        isAvailable(){
            if (this.availableLanguage.includes(this.info.original_language)) {
                return true
            }
            return false
        },
    },
  // creo un array in cui si indicano le bandiere disponibili e nel computed bisogna capire se la lingua è presente o meno all'interno dell'array
  data() {
    return {
      availableLanguage: ["en", "it"],
    };
  },
};
</script>

<style></style>
