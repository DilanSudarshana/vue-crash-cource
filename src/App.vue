<template>
  <router-view />
</template>

<script>
import SignUp from './components/SignUp.vue'

export default {
  name: 'App',
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

}

.logo {
  width: 100px;
}

.container {
  margin: 5px;
}

.row {
  margin: 5px;
}
</style>
