<template>
    <div class="container-fluid">
        <div class="row">
            <div class="col-12 ">
                <h3>Цена: {{elem}}</h3>
            </div>
        </div>        
   </div>
</template>

<script>
export default {
    name: 'TotalPrice',
    data() {
    return {
        totalPrice: 0
    }
    },
    props: ['elem']
}
</script>

<style scoped>

</style>
