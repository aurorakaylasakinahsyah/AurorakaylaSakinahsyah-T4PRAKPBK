<template>
    <div class="product" v-if="product">
      <h3>Detail produk</h3>
      <p>Nama: {{ product.name }}</p>
      <p>Harga: Rp{{ product.harga }}</p>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ProductDetail',
    props: {
      product: Object,
    },
  };
  </script>
  
  <style scoped>
  .product {
    border: 3px solid rgb(203, 124, 173);
    
  }
  </style>
  