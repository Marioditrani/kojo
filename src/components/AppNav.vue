
<script >
  import {state} from '../state.js';

 export default{
  data(){
    return{
      state,
      infomenu: 0,
    }
  },
  methods: {
    infoside() {
        if (this.infomenu) {
            this.infomenu = 0
        } else {
            this.infomenu = 1
        }
        },
    }
 }
</script>


<template>
  <div class="nav">
    <div class="left-nav">
      <div class="img"></div>
      <img src="../assets/img/logo_kojo.jpg" alt="">
    </div>

    <div class="triangolo">
      <div class="triangolo-right">
        
      </div>
    </div>
  
  
    <div class="right-nav">
      <div class="main-nav">
        <div class="bg-nav">
          <router-link :to="{ name: 'home' }" :class="state.actvPage == 1 ? 'active-link' : '' " class="nav-link" @click="state.updateActvPage(1)" >home</router-link>
          <router-link :to="{ name: 'menu' }" :class="state.actvPage == 2 ? 'active-link' : '' " class="nav-link" @click="state.updateActvPage(2)" >menu</router-link>
          <router-link :to="{ name: 'prenota' }" :class="state.actvPage == 5 ? 'active-link' : '' " class="nav-link" @click="state.updateActvPage(5)" >Ordina d'Asporto</router-link>
          <router-link :to="{ name: 'prenotaServizio' }" :class="state.actvPage == 6 ? 'active-link' : '' " class="nav-link" @click="state.updateActvPage(6)" >Prenota tavolo</router-link>
          <div class="t-nav"></div>
        </div>
        <div class="bottom-nav">
          <router-link :to="{ name: 'chi-siamo' }" class="chi-siamo" ><p>Chi siamo?</p></router-link>
          <router-link :to="{ name: 'contatti' }" class="contatti" > <span>Contatti</span></router-link>
          <div class="t-contatti"></div>
        </div>
      </div>
    </div>
  </div>
</template>


<style lang="scss" scoped>
@use '../assets/styles/general.scss' as *;
.nav{
  width: 100%;
  height: 100%;
  display: flex;

  .left-nav{
    min-width: 30%;
    display: flex;
    justify-content: center;
  }
  .triangolo{
    width:0;
    border-left: 0px solid transparent;
    border-right: 150px solid transparent;
    border-bottom: 300px solid white;
    -moz-transform:rotate(0);
    -webkit-transform:rotate(0);
    -ms-transform:rotate(0);
    -o-transform:rotate(0);
    transform:rotate(0);
    background-color: #523333;
  }

  .right-nav{
    width: 70%;
    background-color: #523333;
    
    .main-nav{
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      height: 100%;
      
      .bg-nav{
        background-color: #712A2A;
        display: flex;
        justify-content: space-between;
        width: 100%;
        padding: 25px 150px 25px 45px;
        border: 10px solid white;
        border-right: 0px;
        font-size: 20px;
        text-transform: uppercase;
        margin-top: 85px;
        
      }

      .bottom-nav{
        width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: flex-end;
        
        
        
        
        .contatti, .chi-siamo{
          display: flex;
          justify-content: center;
          align-items: center;
          background-color: #270000;
          width: 200px;
          height: 50px;
          border: 5px solid white;
          
          
        }
        .chi-siamo{
          transform:skew(27deg);
          position: relative;
          bottom: 1px;
          left: -14px;
          z-index: 1;
          
          
          p{
            transform:skew(-30deg);
            
          }
        }
        
        .contatti{
          position: absolute;
          top: 2;
          right: 0;
        }
        .t-contatti{
          height: 50px;
          position: relative;
          top: 2;
          right: 200px;
          width:0;
          border-left: 0px solid transparent;
          border-right: 20px solid transparent;
          border-bottom: 50px solid #523333;
          -moz-transform:rotate(0);
          -webkit-transform:rotate(0);
          -ms-transform:rotate(0);
          -o-transform:rotate(0);
          transform:rotate(0);
          background-color: white;
        }
        
      }
    }
  }
}

@media (max-width:1500px) {
  .nav{
    .right-nav{
      .main-nav{
        .bg-nav{
          padding: 25px 25px 25px 45px;
        }
      }
    }
  }
}
</style>


