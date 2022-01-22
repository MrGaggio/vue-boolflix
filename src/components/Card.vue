<template>
    <!-- :info="card" passa il contenuto dell'oggetto-->
  <div class="cards">
      {{info.title}}
      {{info.original_title}}      
      {{info.original_language}}
      {{info.language}}
      {{info.vote_average}}
      {{info.title}}
  </div>
</template>

<script>
export default {
    name: 'Card',
    //anche per gli oggetti il default deve essere una funzione ma si puo non mettere
    props: {
        info: Object,
    },
}
</script>

<style>

</style>