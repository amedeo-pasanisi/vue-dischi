<template>
  <div id="app">
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
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
