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
<FilmComp/>
<SeriesComp/>
</template>
<style lang="scss" scoped>

</style>