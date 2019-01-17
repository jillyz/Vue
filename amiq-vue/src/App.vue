<template>
  <div id="app">

    <Catalog v-if="true" />

  </div>
</template>

<script>
import Catalog from './components/Catalog.vue';


export default {
  name: 'app',
  components: {
    Catalog,
  }
}
</script>

<style>
#app {
  /* font-family: 'Avenir', Helvetica, Arial, sans-serif; */
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  /* margin-top: 60px; */
}
html, body {
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Roboto','RobotoDraft','Heiti TC','Microsoft JhengHei',Helvetica,Arial,sans-serif;
}
</style>
