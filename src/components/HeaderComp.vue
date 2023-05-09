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
    <img src="/img/Netflix-Logo.png" alt="">
    <div class="input">
      <input type="text" v-model="store.varTesto">
      <button>click me</button>
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
