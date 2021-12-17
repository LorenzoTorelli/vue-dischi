<template>
    <div class="card">
       <img :src="src" :alt="disco">
        <h3><a href="#">{{disco}}</a></h3>
        <h4><a href="#">{{nome}}</a></h4>
        <h5>{{anno}}</h5>
    </div>
</template>

<script>
export default {    
    name:"Card",
    props: {
        src: String,
        disco: String,
        nome: String,
        anno: String,
    }
}
</script>

<style lang="scss" scoped>
    .card {
        // width: 200px;
        padding: 20px;
        // margin: 20px;
        text-align: center;
        background-color: rgb(46,58,70);

        
        img {
               width: 100%;
               margin-bottom: 15px;
        }

        h3 a {
            text-transform: uppercase;
        }
        h3 a ,h4 a {
            text-decoration: none;

            &:hover {
                text-decoration: underline;
            }
        }    
        h3,h4,h5 {
            margin-bottom: 10px;
        }


        h4 a,h5 {
            color: grey;
        }
    }

</style>
