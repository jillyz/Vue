<template>
  <div id="app">
    <!-- <img v-if="false" alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld v-if="false" msg="Welcome to Your Vue.js App" ccc="heyhey"/> -->

    <Catalog v-if="true" />
    <!-- <Game v-if="true" /> -->

  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue';
import Catalog from './components/Catalog.vue';
import Game from './components/Game.vue';


export default {
  name: 'app',
  components: {
    // HelloWorld,
    Catalog,
    Game,
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
