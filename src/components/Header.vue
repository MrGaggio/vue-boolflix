<template>
  <header>
    <div class="search">
      <!-- <label for="search"></label>
      <input v-model="searchText" type="text" placeholder="search" />
      <button @click="$emit('search', searchText)">cerca film</button> -->
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {};
  },
};
</script>

<style>
header {
  height: 100px;
}
</style>
