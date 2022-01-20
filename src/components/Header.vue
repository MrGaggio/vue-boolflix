<template>
  <header>
    <div class="search">
        <label for="search"></label>
        <input
        v-model="searchText" 
        type="text" 
        placeholder="search">
        <button 
        @click="$emit('search', searchText)">cerca film</button>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
    data(){
        return {
            searchText: "",
            queryApi: "https://api.themoviedb.org/3/search/movie?api_key=f0278b0dff056a07e75af2bb599a91bc&query="
        }
    }
};
</script>

<style>
header {
  height: 100px;
}
</style>
