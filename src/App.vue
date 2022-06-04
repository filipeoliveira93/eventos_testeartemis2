<template>
  <img alt="Evento" src="./assets/eventos.png">
  <CadastroComp></CadastroComp>
</template>

<script>
import CadastroComp from './components/Cadastro.vue'

export default {
  name: 'App',
  components: {
    CadastroComp
    
  }
}
</script>

<style>
@import "https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css";
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

img{
  width: 5rem;
  height: auto;
}
</style>
