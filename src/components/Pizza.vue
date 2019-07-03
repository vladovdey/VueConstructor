<template>
    <div class="col-12 col-md-8 text-center">
        <div class="product-container" >
            <div class="selected-product" :key="i" v-for="(product, i) in products">
                <!-- <img v-bind:src="product.icon" /> -->
                <p>{{product.name}}</p>
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
    width: 100%;
    margin: 0 auto;
}

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
