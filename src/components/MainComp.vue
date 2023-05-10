<script>
import {store} from "../store"
import FilmComp from './FilmComp.vue';
import SeriesComp from './SeriesComp.vue';

export default{
    name: "MainComp",
    components: { FilmComp, SeriesComp },
    data(){
        return{
            store,
            
        }
    }
    
}

</script>
<template>
    <div class="box">
        <h1>FILM</h1>
        <div class="cont-80">
            <FilmComp v-for="(elem, index) in store.array"
            :propsFilm="elem" :propsPathFilm="store.pathFilm"/>
        </div>
        <h1>SERIE</h1>
        <div class="cont-80">
            <SeriesComp v-for="(elemento, index) in store.arraySerie"
            :propsSerie="elemento" :propsPathSerie="store.pathFilm"/>
        </div>
    </div>
</template>
<style lang="scss" scoped>
h1{
        color: white;
        padding-left: 180px;
        padding-top: 30px;
        // position: absolute;
        // top: 0;
        // left: 0;
    }
.cont-80{
    width: 80%;
    margin: 0 auto;
    padding: 30px 0;
    overflow-y: scroll;
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: relative;
    
}
</style>