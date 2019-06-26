<template>
  <div id="app">
    <Header />
    <div class="container-fluid">
      <div class="row">
        <ProductTypes v-bind:types="types"/>
        <Pizza />
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
        {id:0 , title:"Мясо"},
        {id:0 , title:"Cыр"},
        {id:0 , title:"Соус"}
      ]  
    }
  },
}
</script>

<style>

</style>
