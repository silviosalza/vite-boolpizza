<script>
import axios from 'axios';
import PizzaCard from '../components/PizzaCard.vue'

export default{
    name:'PizzasList',
    components: {
    PizzaCard,
  },
  data(){
    return{
      pizzas:[]
    }
  },
  mounted(){
    this.getPizza();
  },
  methods: {
    getPizza(){
      axios.get('http://127.0.0.1:8000/api/pizzas').then(resp => {
        this.pizzas = resp.data.results;

      })


    }
  },

}

</script>




<template>
    <div class="row row-cols-4">
        <div class="col" v-for="(pizza,index) in pizzas" :key="index">
            <PizzaCard :pizza="pizza"/>
        </div>

    </div>

</template>

<style lang="scss" scoped>

</style>