<template>
  <div id="app">
    <Header :genres= "genres" @selectedGenre= "selectedGenreToFilter" />
    <Main :filter= "filter" @genres= "createGenresArray"/>
  </div>
</template>

<script>
import Header from "./components/Header"
import Main from "./components/Main"

export default {
  name: 'App',
  data () {
    return {
      filter: "",
      genres: null
    }
  },
  methods: {
    selectedGenreToFilter (selectedGenre) {
      this.filter = selectedGenre
    },
    createGenresArray (genres) {
      this.genres = genres
    }
  },
  components: {
    Header,
    Main
  }
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  height: 100vh;
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
