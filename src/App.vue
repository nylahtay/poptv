<template>
  <div id="app">
    <!-- THis is wher we can set the header text -->
    <Header theTitle="Popular TV Shows"/>

    
    <div class="card-group">
      <!-- use v-for to go through each show in the shows array | also use index so that we can limit to 4 items-->
      <div v-for="(show,index) in shows" v-bind:key="show.id">
        <!-- use v-bind to bind theShow to each show in Shows. | we are using the index to limit to only showing 4 items -->
        <Card v-bind:theShow="show" v-if="index < 4"/>
      </div>
    </div>
  </div>
</template>

<script>
//importing the component for the header
import Header from './components/Header.vue'

//importing the component for the Card
import Card from './components/Card.vue'

//importing Axios
import axios from 'axios'

//importing Bootstrap
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
    //this is the test data that I was working with,
    return {
      shows: [
        {id:1, name:"movie 1", overview: "this is the details of the item 1. Lorum ispms iah aisSd aisdha ankaseihasdklwsej isiadh ihs iais id i haiiha keihab ooak", poster_path: "/sWgBv7LV2PRoQgkxwlibdGXKz1S.jpg"},
        {id:2, name:"The big movie 2", overview: "details of the item 2. Lorum ispmaseihasdklwsej isiadh ihs iais id i h", poster_path: ""}
      ]
    }
  },
  //this is the TV show json.
  mounted()
  {
    axios.get('https://api.themoviedb.org/3/tv/popular?api_key=4cef9861a58f0609b80973fbdbafeb03&language=en-US&page=1')
    .then ( (response) => {
      this.shows = response.data.results;
    })
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
}
</style>
