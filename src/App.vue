<script >
  
  import AppNav from './components/AppNav.vue'
 


  export default {
  components:{  AppNav,  }
  }
</script>

<template>

  <div class="container">
    <AppNav class="appnav"/>
    <router-view class="page"></router-view>
    
  </div>
 

  
</template>

<style lang="scss">
@use './assets/styles/general.scss' as *;






</style>
