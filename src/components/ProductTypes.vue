<template>
    <div class="col-12 col-md-4">
        <div class="elementContainer text-center" :key="type.id" v-for="type in types">
            <p class="category-title">{{type.title}}</p>
            
            <div class="ingridients" :key="ing.id" v-for="ing in type.ingridients">
                <p class="ingridient-title">{{ing.name}}. {{ing.weight}} грамм/порция </p>
                <span class="dop">Кол-во порций </span> <input v-model="ing.porc" type="number" min=1 max=2>
                <p class="dop">Цена: {{ing.price}} руб./порция</p>
                <button @click="$emit('addIngrid',ing)">Добавить ингридиент</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ProductTypes',
    data() {
        return {
            message: 1
        }
    },
    props: ['types'],
    // methods: {
    //     addProduct: function (type){
    //         c
    //     }
    // }

}
</script>

<style scoped>
input{
    width: 30px;
    height: 25px; 
    border: 2px solid;
    font-size: 20px;
}
button{
    border-radius: 10px;
    font-size: 20px;
    background: white;
    border: 2px solid;
    padding: 2px 10px;
    outline: none;
}
.elementContainer{
    color: #fff;
    background-color: #343a40;
    padding: 0px 0px 15px 0px;
    margin-bottom: 15px;
    border-bottom: 1px solid #343a40;
    border-radius: 10px;
    cursor: default;
}

.ingridients{
    border: 1px solid black;
    margin-bottom: 10px;
    padding: 10px 0px;
    background-color: #474747
}

.elementContainer:hover{
    transition-delay: 1s;
    border: none;
}

.category-title{
    font-size: 28px;
}

.ingridient-title{
    font-size: 20px;
}
.dop{
    font-family: 'Helvetica',sans-serif;
    color: #e1e1e1;
    font-size: 15px;
    margin-bottom: 5px;
}
.dop p{
    padding: 0;
}

</style>
