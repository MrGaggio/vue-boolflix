<template>
  <header>
    <div class="search">
      <label for="search"></label>
      <i class="fab fa-500px"></i>
      <input 
      v-model="textSearch" 
      type="text" 
      placeholder="search" />
      <button 
      @click="$emit('searchTesto', textSearch)
      ">cerca film</button>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      textSearch: "",
    };
  },
};
</script>

<style>
header {
  height: 100px;
}
</style>
