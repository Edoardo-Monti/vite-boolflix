<script>
export default{
  name:"HeaderComp"
}
</script>

<template>
  <div class="d-flex justify-content-around align-items-center">
    <img src="../../public/img/Netflix-Logo.png" alt="">
    <div class="input">
      <input  type="text">
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
  }
}
</style>
