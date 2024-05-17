<template>
  <div id="app">
    <ProductSearch />
  </div>
</template>

<script>
import ProductSearch from './components/ProductSearch.vue';

export default {
  name: 'App',
  components: {
    ProductSearch,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #d433ca;
  margin-top: 60px;
}
</style>
