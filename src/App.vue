<template>
  <div id="app">
    <Sidebar />
    <div class="main">
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
import Sidebar from './components/Sidebar'

export default {
  name: 'App',
  components: {
    Sidebar
  }
}
</script>

<style>
body {
  background-color: #444;
}
.main {
  position: absolute;
  right: 0;
  width: 100%;
  max-width: calc(100% - 360px);
  height: 100%;
  background-color: #fff;
  color: #222;
}
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
