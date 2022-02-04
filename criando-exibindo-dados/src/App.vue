<template>
  <div id="app">
    <h1 v-text="nome"></h1>
    <small v-if="mostra" v-once v-text="nome"></small>

    <button @click="mostra = !mostra" :disabled="nome != 'Mineirão'">Trocar</button>

    <input type="text" v-model="nome">

    <ul>
      <li v-for="qnt in cadeiras">{{ qnt }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      nome: 'Mané Garrincha',
      mostra : true,
      cadeiras: [
        '30.000 brancas',
        '30.000 cinzas',
        '10.000 vips',
      ]
    }
  },
  mounted() {
    setTimeout(() => this.nome = 'Mineirão', 4000)
  }
}
</script>

<style scoped>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
 }

 h1, h2 {
  font-weight: normal;
 }

 ul {
  list-style-type: none;
  padding: 0;
 }

 li {
  display: inline-block;
  margin: 0 10px;
 }

 a {
  color: #42b983;
 }
</style>





