<template>
  <div id="app">
    <Header @clickMovies="functionMovies"/>
    <main>
      <Grid :moviesArray= "moviesArray"/>
    </main>
  </div>
</template>

<script>
import Grid from './components/Grid.vue'
import Header from './components/Header.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    Header,
    Grid
  },
  data(){
    return {
      moviesArray: null,
      inputMovie: ''
    }
  },
  created(){
    this.axios()
  },
  methods:{
    axios(){
      axios.get('https://api.themoviedb.org/3/search/movie',{
        params:{
          api_key: '197d0fb590411b5e07fcf33c7772ae5e',
          query: 'Fantozzi',
          language: 'it-IT'
        }
      })
      .then(result =>{
              console.log(result.data.results)
              this.moviesArray = result.data.results
              })
      .catch (err => 
              console.log(err))
},
  functionMovies(text){
    this.inputMovie = text
    console.log(this.inputMovie)
  }
  },
}
</script>

<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-left: 30px;
  margin-top: 30px;
}
</style>
