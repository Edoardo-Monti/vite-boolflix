<script>
import {store} from "../store"

export default{
  name:"HeaderComp",
  data(){
    return{
      store
    }
  }
}
</script>

<template>
  <div class="d-flex justify-content-around align-items-center">
    <a href="/">
      <img src="/img/Netflix-Logo.png" alt="">
    </a>
    <div class="input">
      <input type="text" v-model="store.varTesto" placeholder="  cerca un film" >
      <button @click="$emit('emitFilm')">click me</button>
    </div>
  </div>
</template>

<style lang="scss" scoped>
div{
  height: 60px;
  background-color: black;
  img{
    width: 100px;
  }
  .input{
    height: 30px;
    input{
      border: none;
    }
    button{
      border: none;
    }
  }
}
</style>
