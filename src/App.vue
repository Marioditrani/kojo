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


.page{
  width: 100vw;
  height: 70%;
}


@media (max-width:1100px) {
    
    .page{
      height: 80%!important;
    }
}



</style>
