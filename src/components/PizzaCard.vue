<script>
export default{
    name: "PizzaCard",
    props:{
        pizza: Object,
    },
    computed:{
        
    }
}
</script>

<template>
    <div class="card text-center">
        <h4>{{ pizza.name }}</h4>
        <p>{{ pizza.price }}</p>
        <p>{{ pizza.description }}</p>
        <span v-for="(ingredient,index) in pizza.ingredients">
        <h6>{{ ingredient.name + " " }}</h6></span>
    </div>
</template>

<style scoped lang="scss">

.card{
    height: 180px;
    margin-top: 2rem;
    background-color: rgb(88, 88, 101);
    color: white;
}
</style>