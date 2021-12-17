<template>
  <div id="main">
        <div class="container">
            <Selezioni @cambio = "changeStatus"/>
        </div>

        <div class="container card-container">
            <Card v-for="(elem,index) in filtraSchede" :key="index" 
                :src = "elem.poster"
                :disco = "elem.title"
                :nome = "elem.author"
                :anno = "elem.year"
            />
            
        </div>
  </div>
</template>

<script>
import axios from 'axios';
import Card from '../components/Main-components/Card.vue';
import Selezioni from '../components/Main-components/Selezioni.vue'

export default {
    name:"Main",
    components: { 
        Card,
        Selezioni,
    },
    data() {
         return {
            schede: [],
            filtro: '', 
        }
    },
    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((response) =>{
                // handle success
               this.schede = response.data.response;
            })
            .catch(function (error) {
                // handle error
                console.log(error);
            })
           
    },
    methods: {
        changeStatus(selez) {
            this.filtro = selez;
        }        
    },
    
    computed: {
        filtraSchede() {
            return this.schede.filter( (e) => {
                return e.genre.toLowerCase().includes(this.filtro.toLowerCase())
            })
            
        }
    }
}

</script>

<style lang="scss" scoped>

    #main {
        width: 100%;
        
        .card-container {
            display: grid;
            justify-content: center;
            grid-template-columns: repeat(auto-fill, 200px);
            grid-gap: 30px;
            padding: 30px 0px 60px;
        }
    }
</style>