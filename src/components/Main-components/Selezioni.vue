<template>
    <div id="contenitore">
        <select name="genere" id="genere" v-model="selez" @change="$emit('cambio', selez)">
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
            <option value="">All</option>
        </select>
    </div>
</template>

<script>
export default {
    name: "selezioni",
    data () {
        return {
            selez: '',
        }
    }
}
</script>

<style lang="scss" scoped>

    #contenitore {
        width: 100%;
        text-align: center;
        padding-top: 100px ;

        select {
            background-color: rgb(30,45,59);
            border-radius: 25px;
            width: 150px;
            padding: 5px;
            border: 1px solid white;
        }
    }

</style>

