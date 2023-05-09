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
    <div class="">
        <div class="cont-80">
            <FilmComp v-for="(elem, index) in store.array"
            :propsFilm="elem" :propsPathFilm="store.pathFilm"/>
        </div>
        <div>
            <SeriesComp/>
        </div>
    </div>
</template>
<style lang="scss" scoped>
.cont-80{
    width: 80%;
    margin: 0 auto;
    padding: 30px 0;
    overflow-y: scroll;
    display: flex;
    align-items: center;
    justify-content: space-between;
}
</style>