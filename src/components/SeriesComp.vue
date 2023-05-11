<script>
export default{
    name:"SeriesComp",
    props: ['propsSerie', 'propsPathSerie'],
    data() {
            return {

            }
        },
        created() {
            this.flag
        },
        methods: {
            flag() {
                let flagInput = this.propsSerie.original_language

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
            }
        }
}
</script>
<template>
<div class="box2">
        <img class="img1" :src=" `${propsPathSerie}${propsSerie.poster_path}`" alt="#">
        <div class="card-box">
            <h1> {{ propsSerie.name }}</h1>
            <div class="d-flex">
                <i class="fa-solid fa-star" style="color: #ffee2e;" v-for="(elem, index) in Math.ceil(propsSerie.vote_average / 2)"></i>
    
                <i class="fa-regular fa-star" v-for="(elem, index) in 5 - Math.ceil(propsSerie.vote_average / 2)"></i>
            </div>
            <p><img :src="`https://flagsapi.com/${flag()}/flat/64.png`" alt=""></p>
            <p class="description"> {{ propsSerie.overview }}</p>
            
        </div>
        
    </div>
</template>
<style lang="scss" scoped>
.box2 {
        width: 300px;
        height: 400px;
        // padding: 5px;
        margin: 5px;
        color: white;
        position: relative;
        &:hover{
            .card-box{
                right: 0;
                transition: 1.5s;
            }
        }

        .img1 {
            width: 300px;
            height: 100%;
        }
        .card-box{
            width: 100%;
            height: 400px;
            position: absolute;
            top: 0;
            right: -100%;
            background: #1f3d474b;
            backdrop-filter: blur(4px);
            padding: 10px 30px;
            overflow: scroll;
            h1 {
                margin-top: 30px;
                font-size: 30px;
                font-weight: 500;
                text-transform: uppercase;
            }
            .description{
                font-size: 13px;
                margin: 30px 0;
            }
            p{
                img{
                    width: 20px;
                }
            }
        }

    }
</style>