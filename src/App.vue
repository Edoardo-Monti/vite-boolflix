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
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=3cae1d84aa03d2da64f3fe5b2014b691&query=bat`).then((res) => {

        const dati = res.data.results

        store.array = dati
        // console.log(res.data.results)
      })
    }
  }
}

</script>

<template>
  <div>
    <HeaderComp/>
    <MainComp/>
  </div>
</template>

<style lang="scss">
@use "./style/main.scss";
</style>
