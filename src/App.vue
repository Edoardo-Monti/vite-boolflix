<script >
import HeaderComp from './components/HeaderComp.vue';
import {store} from './store';



export default{
  name: 'App',
  components: {
    HeaderComp
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
  </div>
</template>

<style lang="scss">
@use "./style/main.scss";
</style>
