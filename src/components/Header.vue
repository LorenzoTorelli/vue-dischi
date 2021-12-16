<template>
    <div id="header">
        <div><img src="../assets/img/logo-small.svg" alt=""></div>
    </div>
</template>

<script>
export default {
    name:"Header",
}
</script>

<style lang="scss" scoped>
// @import url("../assets/Partials.scss");
    #header {
        width: 100%;
        height: 60px;
        // background-color: $Main-color;
        background-color: rgb(46,58,70);
        display: flex;
        position: fixed;
        div {
            width: 40px;
            align-self: center;
            margin-left: 15px;
            img {
                object-fit: contain;
                // color: rgb(30, 215, 96);
        }
        }
        
    }
</style>>
