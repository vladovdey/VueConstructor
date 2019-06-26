<template>
    <div class="col-12 col-md-4">
        <div class="elementContainer text-center" :key="type.id" v-for="type in types">
            <p>{{type.title}}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ProductTypes',
    props: ['types']
}
</script>

<style scoped>
.elementContainer{
    color: #fff;
    background-color: gray;
    padding: 0px;
    border-bottom: 1px solid black;
    cursor: pointer;
}
</style>
