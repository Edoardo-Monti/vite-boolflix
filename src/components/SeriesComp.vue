<script>
export default{
    name:"SeriesComp",
    props: ['propsSerie', 'propsPathSerie']
}
</script>
<template>
<div class="box2">
        <img :src=" `${propsPathSerie}${propsSerie.poster_path}`" alt="#">
        <h1><mark>TITOLO:</mark> {{ propsSerie.name }}</h1>
        <h2><mark>TITOLO ORIGINALE:</mark> {{ propsSerie.name }}</h2>
        <p><mark>LINGUA:</mark> {{ propsSerie.original_language }}</p>
        <p><mark>VOTO:</mark> {{ propsSerie.vote_average }}</p>
    </div>
</template>
<style lang="scss" scoped>
.box2 {
        // background-image: url('https://image.tmdb.org/t/p/w342/1QJ2ooSZ6Ij6oPVyYtp7HLieW6f.jpg');
        // background-repeat: none;
        // background-size: cover;
        min-width: 200px;
        min-height: 550px;
        // border: 1px solid black;
        padding: 10px;
        margin: 15px;
        color: white;

        img {
            width: 100%;
        }

        h1 {
            margin-top: 10px;
            font-size: 15px;
        }

        h2 {
            color: white;
            font-size: 15px;
        }
    }
</style>