<template>
  <div id="app">
    <Header />
    <div class="container-fluid content">
      <div class="row">
        <ProductTypes @addIngrid="addPizza" v-bind:types="types" />
        <Cart @delIngrid="delPizza" :cartProducts="selectedProduct" :totalPrice="price" />
      </div>
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import ProductTypes from "./components/ProductTypes.vue";
import Cart from "./components/Cart.vue";

export default {
  name: "app",
  components: {
    Header,
    ProductTypes,
    Cart
  },
  data() {
    return {
      types: [
        {
          catId: 0,
          title: "Сыр",
          ingridients: [
            {
              prodId: 3,
              category: 1,
              name: "Пармезан",
              price: 60,
              porc: 1,
              weight: 30,
              img: require('./assets/ingrid/cheese.png')
            },
            {
              prodId: 4,
              category: 1,
              name: "Моцарелла",
              price: 30,
              porc: 1,
              weight: 20,
              img: require('./assets/ingrid/cheese.png')
            }
          ]
        },
        {
          catId: 1,
          title: "Мясо",
          ingridients: [
            {
              prodId: 1,
              category: 0,
              name: "Курица",
              price: 100,
              porc: 1,
              weight: 20,
              img: require('./assets/ingrid/kuritsa.png')
            },
            {
              prodId: 2,
              category: 0,
              name: "Салями",
              price: 120,
              porc: 1,
              weight: 20,
              img: require('./assets/ingrid/salyami.png')
            }
          ]
        },
        {
          catId: 2,
          title: "Овощи",
          ingridients: [
            {
              prodId: 5,
              category: 2,
              name: "Помидор",
              price: 10,
              porc: 1,
              weight: 20,
              img: require('./assets/ingrid/pomido.png')
            },
            {
              prodId: 6,
              category: 2,
              name: "Перец",
              price: 5,
              porc: 1,
              weight: 20,
              img: require('./assets/ingrid/perez.png')
            }
          ]
        }
      ],
      price: 85,
      selectedProduct: [
        //{ prodId: 0, name: "Основа пиццы", price: 85, weight: 100, porc: 1 }
      ]
    };
  },
  methods: {
    addPizza(elem) {
      let addbool = true;
      
      if (this.selectedProduct.length == 0) {
        this.selectedProduct.push(elem);
      } else {
        this.selectedProduct.forEach(function(arrayElem) {
          if (arrayElem.prodId == elem.prodId) {
            addbool = false;
          }
        });
        if (addbool == true) {
          this.selectedProduct.push(elem);
        } else {
          addbool = true;
        }
      }

      this.price = calc(this.selectedProduct);
      console.log(this.price);

      function calc(array){
        let sum=0;
        array.forEach(elem=>{
          sum += elem.price*elem.porc;
        });
        return sum+85;
      }  
    },
    
    delPizza(product) {
      if (product.prodId != 0) {
        let delIndex = 1;
        this.selectedProduct.forEach(function(elem, index) {
          if (elem.prodId == product.prodId) {
            delIndex = index;
          }
        });
        this.selectedProduct.splice(delIndex, 1);
        
      }
    }
  }
};
</script>

<style>
.content{
  margin-top: 20px;
}

:active,
:hover,
:focus {
  outline: 0;
  outline-offset: 0;
}
</style>
