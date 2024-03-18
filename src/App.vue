<template>
  <DesafioPi msg="DESAFÍO MATEMÁTICO: PIFILOLOGÍA"></DesafioPi>
</template>

<script>
import DesafioPi from "./components/DesafioPi.vue";

export default {
  name: 'App',
  components: { DesafioPi }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
