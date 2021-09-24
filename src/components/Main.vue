<template>
    <main id="dischi">
        <div class="container">
            <Disco 
                v-for= "(disco,index) in filteredDischi"
                :key= "index"
                :disco= "disco"
            />
        </div>
    </main>
</template>

<script>
import axios from "axios";
import Disco from "./Disco"
export default {
    name: 'Main',
    components: {
        Disco
    },
    props: {
        filter: String
    },
    data() {
        return {
            apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
            dischi: null,
            genres: []
        }
    },
    computed: {
        filteredDischi () {
            if (this.filter == "") {
                return this.dischi
            }
            return this.dischi.filter(
                (disco) => disco.genre == this.filter
            );
        }
    },
    methods: {
        getApi() {
            axios 
                .get (this.apiUrl)
                .then ((result) => {
                    this.dischi = result.data.response;

                    this.dischi.forEach((disco) => {
                        if (!this.genres.includes(disco.genre)) {
                            this.genres.push(disco.genre);
                        }
                    })

                    this.$emit("genres", this.genres);
                })
                .catch((errore) => {
                    alert(errore);
                });
        }
    },
    created() {
        this.getApi();
    },
}
</script>

<style scoped lang="scss">
    #dischi {
        height: 90%;
        background-color: #1E2D3B;
        padding: 60px 0;
        .container {
            width: 50%;
            height: 100%;
            margin: auto;
            display: flex;
            align-content: space-between;
            flex-wrap: wrap;
        }
    }
</style>