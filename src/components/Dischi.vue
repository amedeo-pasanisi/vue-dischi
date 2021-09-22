<template>
    <div id="dischi">
        <div class="container">
            <Disco 
                v-for= "(disco,index) in dischi"
                :key= "index"
                :disco= "disco"
            />
        </div>
    </div>
</template>

<script>
import axios from "axios";
import Disco from "./Disco"

export default {
    name: 'Dischi',
    components: {
        Disco
    },
    data() {
        return {
            dischi: null
        }
    },
    beforeCreate() {
        axios 
            .get ("https://flynn.boolean.careers/exercises/api/array/music")
            .then ((result) => {
                this.dischi = result.data.response;
            });
    }
}
</script>

<style lang="scss">
    #dischi {
        height: 90%;
        background-color: #1E2D3B;
        padding: 60px 0;
        .container {
            width: 50%;
            height: 100%;
            margin: auto;
            display: flex;
            justify-content: space-between;
            align-content: space-between;
            flex-wrap: wrap;
        }
    }
</style>