<template>
    <div class="col-12 col-md-8 text-center">
        <div class="product-container text-center">
            <div class="selected-product" :key="i" v-for="(product, i) in products">
                <p>{{product.title}}</p>
            </div>
        </div>
        <img src="../assets/pizza.png" alt="pizzaimg">
    </div>
</template>


<script>
export default {
    name: 'pizza',
    props: ['products']
}
</script>

<style scoped>
.product-container{
    position: absolute;
}
 img{
     position: relative;
     height: 500px;
     width: 500px;
     z-index: 0;
 }
</style>
