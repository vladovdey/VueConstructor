<template>
  <div id="app">
    <Header />
    <div class="container-fluid">
      <div class="row">
        
        <ProductTypes @addIngrid="addPizza" v-bind:types="types"/>
        
        <Pizza v-bind:products='selectedProduct'/>
      </div>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import ProductTypes from './components/ProductTypes.vue'
import Pizza from './components/Pizza.vue'


export default {
  name: 'app',
  components: {
    Header,
    ProductTypes,
    Pizza
  },
  data() {
    return {
      types: [
        {id:0 , title:"Мясо", price: 12 },
        {id:1 , title:"Cыр", price: 15 },
        {id:2 , title:"Соус", price: 6 }
      ],
      selectedProduct: []
    }
  },
  methods: {
    addPizza(elem){
      this.selectedProduct.push(elem);
    }
  }
}
</script>

<style>

</style>
