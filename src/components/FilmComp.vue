<script>
export default{
    name:"FilmComp",
    props:['propsFilm']
}
</script>
<template>
<div class="box1">
    <h1><mark>TITOLO:</mark> {{ propsFilm.title }}</h1>
    <h2><mark>TITOLO ORIGINALE:</mark> {{ propsFilm.original_title }}</h2>
    <p><mark>LINGUA:</mark>  {{ propsFilm.original_language }}</p>
    <p><mark>VOTO:</mark>  {{ propsFilm.vote_average }}</p>
</div>
</template>
<style lang="scss" scoped>
.box1{
    min-width: 200px;
    height: 300px;
    border: 1px solid black;
    padding: 10px;
    margin: 15px;
    h1{
        font-size: 15px;
    }
    h2{
        font-size: 15px;
    }
}
</style>