<template>
    <div class="col-12 col-md-4">
        <div class="elementContainer text-center" :key="type.id" v-for="type in types">
            <p>{{type.title}} Цена: {{type.price}} руб.</p>
            <button @click="$emit('addIngrid',type)">Добавить ингридиент</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ProductTypes',
    props: ['types'],
    // methods: {
    //     addProduct: function (type){
    //         c
    //     }
    // }

}
</script>

<style scoped>
.elementContainer{
    color: #fff;
    background-color: gray;
    padding: 0px 0px 5px 0px;
    margin: 5px;
    border-bottom: 1px solid black;
    cursor: default;
}

.elementContainer:hover{
    transition-delay: 1s;
    border: none;
}

button{
    border: none;
    outline: none;
}
</style>
