<template>
    <div id="dischi">
        <Disco 
            v-for= "(disco,index) in dischi"
            :key= "index"
            :disco= "disco"
        />
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

</style>