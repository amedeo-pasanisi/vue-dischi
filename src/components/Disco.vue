<template>
    <div id="disco">
        <img :src= "disco.poster" alt="">
        <h3>{{disco.title}}</h3>
        <div>{{disco.author}}</div>
        <div>{{disco.year}}</div>
    </div>
</template>

<script>
export default {
    name: "Disco",
    props: ["disco"]
}
</script>

<style scoped lang="scss">
    #disco {
        display: flex;
        align-items: center;
        text-align: center;
        flex-direction: column;
        width: 130px;
        height: 250px;
        padding: 10px;
        background-color: #424c55;
        img {
            width: 100%;
            margin-bottom: 10px;
        }
        h3 {
            color: white;
        }
        div{
            color: gray;
        }
    }
</style>