<script>
  import HeaderComp from './components/HeaderComp.vue';
  import MainComp from './components/MainComp.vue';
  import {
    store
  } from './store';
  import axios from 'axios';



  export default {
    name: 'App',
    components: {
      HeaderComp,
      MainComp
    },
    data() {
      return {
        store
      }
    },
    created() {
      this.apiFilms()
    },
    methods: {
      apiFilms() {

        if (store.varTesto == "") {
          axios.get(`https://api.themoviedb.org/3/movie/popular?api_key=3cae1d84aa03d2da64f3fe5b2014b691`).then((
          res) => {

            const dati = res.data.results

            store.array = dati
            // console.log(res.data.results)

          })
          axios.get(`https://api.themoviedb.org/3/tv/popular?api_key=3cae1d84aa03d2da64f3fe5b2014b691`).then((resp) => {

            const datiSerie = resp.data.results

            store.arraySerie = datiSerie

          })

        } else {
          axios.get(
            `https://api.themoviedb.org/3/search/movie?api_key=3cae1d84aa03d2da64f3fe5b2014b691&query=${store.varTesto}`
            ).then((res) => {

            const dati = res.data.results

            store.array = dati
            // console.log(res.data.results)
          })
          axios.get(
              `https://api.themoviedb.org/3/search/tv?api_key=3cae1d84aa03d2da64f3fe5b2014b691&query=${store.varTesto}`)
            .then((resp) => {

              const datiSerie = resp.data.results

              store.arraySerie = datiSerie

            })
        }
        store.varTesto = ""
      }
    }
  }
</script>

<template>
  <div>
    <HeaderComp @emitFilm="apiFilms" />
    <div class="bg-color">
      <MainComp />
    </div>
  </div>
</template>

<style lang="scss">
  @use "./style/main.scss";

  .bg-color {
    background-color: rgb(34, 34, 34);
    // height: 100vh;
  }
</style>