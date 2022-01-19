<template>
  <dir>

  </dir>
</template>

<script>
import axios from "axios"

export default {
  name: "Main",

  data() {
    return {
        
    };
  },
  methods: {
      searchFilm () {
        axios.get('https://api.themoviedb.org/3/search/movie?api_key=f0278b0dff056a07e75af2bb599a91bc&query=' + 'inputText che sta su Header')
        .then()
        .catch()
      }
  }
};
</script>

<style></style>
