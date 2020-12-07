<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <Header theTitle="Welcome to Your Vue.js App"/>
    <div v-for="show in shows" v-bind:key="show.id" class="card-group">
      <Card v-bind:theShow="show"/>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Card from './components/Card.vue'
import 'bootstrap'
import 'bootstrap/dist/css/bootstrap.min.css'

export default {
  name: 'App',
  components: {
    Header,
    Card
  },
  data()
  {
    return {
      shows: [
        {id:1, name:"movie 1", overview: "this is the details of the item 1. Lorum ispms iah aisSd aisdha ankaseihasdklwsej isiadh ihs iais id i haiiha keihab ooak", poster_path: ""},
        {id:2, name:"The big movie 2", overview: "details of the item 2. Lorum ispmaseihasdklwsej isiadh ihs iais id i h", poster_path: ""}
      ]
    }
  },
  mounted()
  {
    
  }
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
