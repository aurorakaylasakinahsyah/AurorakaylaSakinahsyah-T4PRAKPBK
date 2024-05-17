<template>
  <div>
    <h3>Produk Yang Tersedia</h3>
    <ul>
      <li v-for="product in products" :key="product.id">
        <button @click="selectProduct(product)">
          {{ product.name }} - Rp{{ product.harga }}
        </button>
      </li>
    </ul>
    <slot name="selected-product"></slot>
  </div>
</template>

<script>
export default {
  name: 'ProductList',
  props: {
    products: Array,
  },
  methods: {
    selectProduct(product) {
      this.$emit('select-product', product);
    },
  },
};
</script>

<style scoped>
ul {
  list-style-type: none;
  padding: 0;
}
button {
  display: block;
  width: 20%;
  padding: 10px;
  margin: 0 auto 10px auto;
  margin-bottom: 10px;
  border: 2px solid #ccc;
  background-color: #f9f9f9;
  cursor: pointer;
  border-radius: 4px;
}
button:hover {
  background-color: #e0e0e0;
}
</style>
