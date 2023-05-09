<script >
import HeaderComp from './components/HeaderComp.vue';
import MainComp from './components/MainComp.vue';
import {store} from './store';



export default{
  name: 'App',
  components: {
    HeaderComp,
    MainComp
},
  data(){
    return{
      store
    }
  }
}

</script>

<template>
  <div>
    <HeaderComp/>
    <MainComp/>
  </div>
</template>

<style lang="scss">
@use "./style/main.scss";
</style>
