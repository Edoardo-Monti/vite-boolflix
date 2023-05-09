<script >
import HeaderComp from './components/HeaderComp.vue';
import MainComp from './components/MainComp.vue';
import {store} from './store';
import axios from 'axios';



export default{
  name: 'App',
  components: {
    HeaderComp,
    MainComp
},
  data(){
    return{
      store
    }
  },
  created(){
    this.apiFilms()
  },
  methods:{
    apiFilms(){
      if(store.varTesto == ""){
        axios.get(`https://api.themoviedb.org/3/movie/popular?api_key=3cae1d84aa03d2da64f3fe5b2014b691`).then((res) => {
  
          const dati = res.data.results

          store.array = dati
          // console.log(res.data.results)
        })
      }else{
        axios.get(`https://api.themoviedb.org/3/search/movie?api_key=3cae1d84aa03d2da64f3fe5b2014b691&query=${store.varTesto}`).then((res) => {
  
          const dati = res.data.results
  
          store.array = dati
          // console.log(res.data.results)
        })
      }
    }
  }
}

</script>

<template>
  <div>
    <HeaderComp @emitFilm="apiFilms"/>
    <MainComp/>
  </div>
</template>

<style lang="scss">
@use "./style/main.scss";
</style>
