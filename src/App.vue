<template>
  <div id="app">
    <header>
      <img src="./assets/Spotify.png" alt="">
    </header>
    <Dischi />
  </div>
</template>

<script>
import Dischi from "./components/Dischi"

export default {
  name: 'App',
  components: {
    Dischi
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
  header {
    height: 10%;
    background-color: #424c55;
    display: flex;
    align-items: center;
    img {
      height: 50%;
      margin-left: 20px;
    }
  }
}
</style>
