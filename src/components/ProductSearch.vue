<template>
  <div class="search">
    <h2>Mini Market Happy</h2>
    <input v-model="searchQuery" placeholder="Masukkan Nama Produk" />
    <button @click="searchProducts">Cari</button>

    <ProductList :products="products" @select-product="handleProductSelect">
      <template v-slot:selected-product>
        <ProductDetail v-if="selectedProduct" :product="selectedProduct" />
      </template>
    </ProductList>
  </div>
</template>

<script>
import ProductList from './ProductList.vue';
import ProductDetail from './ProductDetail.vue';

export default {
  name: 'ProductSearch',
  components: {
    ProductList,
    ProductDetail,
  },
  data() {
    return {
      searchQuery: '',
      products: [],
      selectedProduct: null,
    };
  },
  methods: {
    searchProducts() {
      console.log("Tombol cari diklik, query:", this.searchQuery);
      // Simulasi pencarian produk berdasarkan searchQuery
      const allProducts = [
        { id: 1, name: 'apel', harga: 5000 },
        { id: 2, name: 'pisang', harga: 8000 },
        { id: 3, name: 'jeruk', harga: 10000 },
        { id: 4, name: 'sprite', harga: 9000 },
        { id: 5, name: 'gula', harga: 15000 },
        { id: 6, name: 'beras', harga: 120000 },
        { id: 7, name: 'gula merah', harga: 23000 }
      ];
      // Filter produk berdasarkan searchQuery
      this.products = allProducts.filter(product =>
        product.name.toLowerCase().includes(this.searchQuery.toLowerCase())
      );
      console.log("Hasil pencarian:", this.products);
    },
    handleProductSelect(product) {
      this.selectedProduct = product;
    },
  },
};
</script>

<style scoped>
.search {
  border: 5px solid rgb(124, 72, 124);
  padding: 10px;
  margin-top: 20px;
  border-radius: 4px;
  background-color: rgba(234, 224, 235, 0.662); /* Warna latar belakang dengan transparansi */
}

body {
  color: #cb389a;
}

input {
  padding: 8px;
  margin-right: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
}
button {
  padding: 8px 12px;
  border: none;
  background-color: #ff00a2;
  color: white;
  cursor: pointer;
  border-radius: 4px;
}
button:hover {
  background-color: #df96d7;
}
</style>
