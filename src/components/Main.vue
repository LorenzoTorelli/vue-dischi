<template>
  <div id="main">
      <div class="container card-container">
          <Card v-for="(elem,index) in schede" :key="index" 
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

export default {
    name:"Main",
    components: { 
        Card
     },
     data() {
         return {
            schede: null
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
           
     }
    
}
</script>

<style lang="scss" scoped>

    #main {
        background-color: rgb(30,45,59);
        height: 100vh;
        width: 100%;
        padding-top: 60px;
        
        .card-container {
            margin-top: 100px;
            // background-color: red;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
        }
    }
</style>