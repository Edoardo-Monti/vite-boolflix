<script>
import {store} from "../store"
import FilmComp from './FilmComp.vue';
import SeriesComp from './SeriesComp.vue';

export default{
    name: "MainComp",
    components: { FilmComp, SeriesComp },
    data(){
        return{
            store
        }
    }
    
}

</script>
<template>
<FilmComp v-for="(elem, index) in store.array"
:propsFilm="elem"/>
<SeriesComp/>
</template>
<style lang="scss" scoped>

</style>