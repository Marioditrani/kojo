
<script >
  import {state} from '../state.js';

 export default{
  data(){
    return{
      state,
    }
  },

 }
</script>


<template>
 <div class="cont-btn">
   <div class="btn-menu" @click="state.openside" :class="state.sideMenuValue? 'btn-off' : 'btn-on'">
    <div class="l1"></div>
    <div class="l2"></div>
    <div class="l1"></div>
  </div>

 </div>
    
</template>
<!-- 


<span>16:00 - 22:00</span> -->
<style lang="scss" scoped>
@use '../assets/styles/general.scss' as *;



    .btn-menu{
      display: none;
      position: absolute;
      right: 50px;
      top: 50px;
      z-index: 20;

      flex-direction: column;
      gap: 1rem;
      align-items: flex-end;
      .l1{
        width: 40px;
        height: 5px;
        border-radius: 20px;
        background-color: white;
        
      }
      .l2{
        width: 50px;
        height: 5px;
        border-radius: 20px;
        background-color: white;
       
      }
      
    }
    
    
    @media (max-width:$bp1) {.btn-menu{display:flex !important;}}
    .btn-off{
      display: none!important;
    }
</style>