<template>
  <div class="col-12 col-md-8">
    <div class="img">
      <img class="ingrid" v-for="product in cartProducts" :src="product.img" :key="product.prodId" >
      <img src="../assets/pizza.png" alt="pizzaimg">
    </div>

    <h3>Ваша пицца</h3>

    <table class="table table-bordered table-hover">
      <thead class="thead-dark">
        <th>Ингридиент</th>
        <th>Цена</th>
        <th>Вес</th>
      </thead>
      <tbody>
        <tr>
          <td>Основа пиццы</td>
          <td>85 руб.</td>
          <td>150 г.</td>
        </tr>
        <tr @click="$emit('delIngrid',product)" :key="product.prodId" v-for="product in cartProducts">
          <td>{{product.name}}</td>
          <td>{{product.price * product.porc}} руб.</td>
          <td>{{product.weight*product.porc}} г.</td>
        </tr>
      </tbody>
    </table>

    <div> 
      <p>Итоговая цена: {{totalPrice}} руб.</p>   
      <button>Сделать заказ</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Cart",
  props: {
    cartProducts: {
      type: Array
    },
    totalPrice: {
      type: Number
    }
  },
};
</script>

<style scoped>
.img{
  text-align: center;
}

button{
    border-radius: 10px;
    font-size: 20px;
    background: white;
    border: 2px solid;
    padding: 2px 10px;
    outline: none;
}

.ingrid{
 position: absolute; 
}
</style>
