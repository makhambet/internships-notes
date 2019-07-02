<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
  import all from './all'
  export default {
    data() {
      return {
        visible: true
      }
    },
  }
</script>

<style>
  body{
    margin: 0;
    padding: 0;
    font-size: 20px;
    position: relative;
    width: 100%;
    height: 100vh;
  }
  #app{
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    min-height: 500px;
    border: 1px solid #000;
    width: 400px;
    padding: 0 2%;
  }
  .home, .about{
    /* width: 90%; */
    /* margin: 0 auto; */
  }
</style>
