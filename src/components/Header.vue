<template>
  <header>
    <div class="search">
        <label for="search"></label>
        <input
        v-model="inputText" 
        type="text" 
        placeholder="search">
        <button>cerca film</button>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
    data(){
        return {
            inputText: "",
        }
    }
};
</script>

<style>
header {
  height: 100px;
}
</style>
