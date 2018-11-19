<template>
  <div id="app">
    <div>
      <invertir />
    </div>
    <hr>
    <div>
      <bienvenido />
    </div>
    <hr>
    <div>
      <suma />
    </div>
    <hr>
    <div>
      <validaciones />
    </div>
    <hr>
    <div>
      <experiencia />
    </div>
    <hr>
    <div>
      <restaurantes />
    </div>
  </div>
</template>

<script>
import invertir from './components/revertir.vue'
import bienvenido from './components/bienvenido.vue'
import suma from './components/suma.vue'
import validaciones from './components/validaciones.vue'
import experiencia from './components/experiencia.vue'
import restaurantes from './components/restaurantes.vue'

export default {
  name: 'app',
  components: {
    invertir,
    bienvenido,
    suma,
    validaciones,
    experiencia,
    restaurantes
  }
}
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    margin-top: 60px;
  }

  .contenedor-componente
  {
    width: 90%;
    margin: calc(10% / 2);
  }

  .contenedor-principal
  {
    width: 100%;
    border: 1px solid;
    border-radius: 5px;
    padding: 10px;
    box-sizing: content-box;
    height: 150px;
    overflow-y: auto;
  }

  .contenedor-secundario
  {
    border: 1px solid;
    border-radius: 5px;
    float: left;
    padding: 10px;
    margin: 10px;
    box-sizing: content-box;
    width: 29%;
  }
</style>
