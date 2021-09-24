<template>
    <header>
        <img src="../assets/Spotify.png" alt="">
        <select 
            v-model= "selectedGenre"
            @change= "$emit('selectedGenre', selectedGenre)"
            >
            <option value="">Select</option>
            <option 
                v-for= "(genre, index) in genres" 
                :key= "index" 
                :value= "genre">
                {{genre}}
            </option>
        </select>
    </header>
</template>

<script>
export default {
    name: 'Header',
    data() {
        return {
            selectedGenre: ""
        }
    },
    props: {
        genres: Array
    }
}
</script>

<style scoped lang="scss">
    header {
    height: 10%;
    background-color: #424c55;
    display: flex;
    justify-content: space-between;
    align-items: center;
        img {
            height: 50%;
            margin-left: 20px;
        }
        select {
            padding: 10px 20px;
            margin-right: 50px;
            border-radius: 5px;
        }
    }
</style>