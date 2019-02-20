<template>
  <div id="app">
    <img class="logo" alt="Vue logo" src="./assets/logo.png">
    <h1 class="title">Prueba técnica Frontend</h1>
    <h2 class="subtitle">Gabriel Vial</h2>
    <AxiosUser/>
  </div>
</template>

<script>
import AxiosUser from './components/AxiosUser.vue'

export default {
  name: 'app',
  components: {
    AxiosUser
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.logo{
    max-width: 5em;
  }
</style>
