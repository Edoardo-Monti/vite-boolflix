<script>
    export default {
        name: "FilmComp",
        props: ['propsFilm', 'propsPathFilm'],
        data() {
            return {

            }
        },
        created() {
            this.flag
        },
        methods: {
            flag() {
                let flagInput = this.propsFilm.original_language

                if (flagInput == 'en') {
                    flagInput = 'gb'
                } else if (flagInput == 'ja') {
                    flagInput = 'jp'
                } else if (flagInput == 'zh') {
                    flagInput = 'cn'
                }else{
                    flagInput = 'fr'
                }
                let flag = flagInput.toUpperCase()
                return flag
            },
            vote(){
                
            }
        }
    }
    
</script>
<template>
    <div class="box1">
        <img class="img1" :src=" `${propsPathFilm}${propsFilm.poster_path}`" alt="#">
        <h1><mark>TITOLO:</mark> {{ propsFilm.title }}</h1>
        <h2><mark>TITOLO ORIGINALE:</mark> {{ propsFilm.original_title }}</h2>
        <p><mark>LINGUA:</mark> <img :src="`https://flagsapi.com/${flag()}/flat/64.png`" alt=""></p>
        <p><mark>VOTO:</mark> {{ propsFilm.vote_average }}</p>
        
    </div>
</template>
<style lang="scss" scoped>
    .box1 {
        // background-image: url('https://image.tmdb.org/t/p/w342/1QJ2ooSZ6Ij6oPVyYtp7HLieW6f.jpg');
        // background-repeat: none;
        // background-size: cover;
        min-width: 200px;
        min-height: 550px;
        // border: 1px solid black;
        padding: 10px;
        margin: 15px;
        color: white;

        .img1 {
            width: 100%;
        }

        h1 {
            margin-top: 10px;
            font-size: 15px;
        }

        h2 {
            font-size: 15px;
        }
    }
</style>