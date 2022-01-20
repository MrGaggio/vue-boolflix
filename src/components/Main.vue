<template>
  <dir>

  </dir>
</template>

<script>
import axios from "axios"

export default {
  name: "Main",

  props: {
    msg: String,
  },

  data() {
    return {
        films: [],
        queryApi: "https://api.themoviedb.org/3/search/movie?api_key=f0278b0dff056a07e75af2bb599a91bc&query="
    };
  },
    mounted (){
      
      axios.get (`${this.queryApi}${this.msg}/`)
      .then((result) => {
        console.log(result);
      })
    }
  

}
</script>

<style></style>
