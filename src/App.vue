<template>
  <div id="app">
    <Regras/>
    <hr>
        <h3>Insira o tamanho  das paredes de seu quarto.</h3>
    <table>
      <td>
        <Parede01/>
      </td> 
      <td>
        <Parede02/>
      </td> 

      <td>
        <Parede03/>
      </td> 

      <td>
        <Parede04/>
      </td> 
    </table>


  </div>
</template>

<script>
import Regras from './components/Regras.vue'
import Parede01 from './components/Parede.vue'
import Parede02 from './components/Parede02.vue'
import Parede03 from './components/Parede03.vue'
import Parede04 from './components/Parede04.vue'

export default {
  name: 'App',
  components: {
    Regras,
    Parede01,
    Parede02,
    Parede03,
    Parede04,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  text-align: left;
}


</style>
