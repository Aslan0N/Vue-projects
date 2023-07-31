<template>
  <div id="app">
    <AddProduct @add-prod="addProduct"/>
    <ProductList @delete-prod="deleteProduct" :products="products"/>
  </div>
</template>

<script>
import AddProduct from './Components/AddProduct.vue';
import ProductList from './Components/ProductList.vue';
export default {
  name: 'App',
  components:{
    AddProduct,ProductList
  },
  data() {
    return {
      products: [
        { id: 1, categoryId: 1, productName: "Laptop", quantityPerUnit: "Acer Laptop", unitPrice: 3000, unitInStock: 2 },
        { id: 2, categoryId: 1, productName: "Mouse", quantityPerUnit: "Acer Mouse", unitPrice: 30, unitInStock: 4 },
        { id: 3, categoryId: 1, productName: "Keyboard", quantityPerUnit: "Acer Keyboard", unitPrice: 300, unitInStock: 20 }
      ]
    }
  },
  methods: {
    deleteProduct(product){
      this.products = this.products.filter(prod => prod.id !== product.id)
    },
    addProduct(product){
      const newProduct = {...product}
      this.products = {...this.products, newProduct}
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #104272;
  margin-top: 60px;
}
</style>
