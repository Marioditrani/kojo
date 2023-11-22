
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
      <div class="img">

        <img src="../assets/img/logo_kojo.jpg" alt="">
      </div>
    </div>
    <div class="t-mb"></div>
    <div class="right-nav">
      <div class="link">
        <router-link :to="{ name: 'home' }" :class="state.actvPage == 1 ? 'active-link' : '' " class="nav-link" @click="state.updateActvPage(1)" >home</router-link>
        <router-link :to="{ name: 'menu' }" :class="state.actvPage == 2 ? 'active-link' : '' " class="nav-link" @click="state.updateActvPage(2)" >menu</router-link>
        <router-link :to="{ name: 'prenota' }" :class="state.actvPage == 5 ? 'active-link' : '' " class="nav-link" @click="state.updateActvPage(5)" >Ordina d'Asporto</router-link>
        <router-link :to="{ name: 'prenotaServizio' }" :class="state.actvPage == 6 ? 'active-link' : '' " class="nav-link" @click="state.updateActvPage(6)" >Prenota tavolo</router-link>
        <router-link :to="{ name: 'chi-siamo' }" class="chi-siamo" ><p>Chi siamo?</p></router-link>
        <router-link :to="{ name: 'contatti' }" class="contatti" > <span>Contatti</span></router-link>
      </div>
      
      <div class="bg-mb">

      </div>
    </div>
  </div>

  <div :class="state.sideMenuValue ? 'nav-mb-on' : 'nav-mb-off'">
    <div :class="state.sideMenuValue ? 'burger-close-on' : 'burger-close-off'" @click="state.openside">
      <div class="line"  :class="state.infomenu ?   'menu-off': 'active-link' "></div>
      <div class="line l1" :class="state.infomenu ?   'menu-off': 'active-link' "></div>
    </div>
    <div :class="state.sideMenuValue ? 'top-on' : 'top-off'">
      <router-link :to="{ name: 'home' }" :class="state.infomenu ?   'menu-off': 'active-link' " class="nav-link" @click="state.updateActvPage(1)" >home</router-link>
      <router-link :to="{ name: 'menu' }" :class="state.infomenu ? 'menu-off': 'active-link' " class="nav-link" @click="state.updateActvPage(2)" >menu</router-link>
      <router-link :to="{ name: 'chi-siamo' }" :class="state.infomenu ? 'menu-off': 'active-link' " class="nav-link" @click="state.updateActvPage(3)" >chi siamo?</router-link>
      <router-link :to="{ name: 'contatti' }" :class="state.infomenu ? 'menu-off': 'active-link' " class="nav-link" @click="state.updateActvPage(4)" >contatti</router-link>
      <router-link :to="{ name: 'prenota' }" :class="state.infomenu ? 'menu-off': 'active-link' " class="nav-link" @click="state.updateActvPage(5)" >Ordina d'Asporto</router-link>
      <router-link :to="{ name: 'prenotaServizio' }" :class="state.infomenu ? 'menu-off': 'active-link' " class="nav-link" @click="state.updateActvPage(6)" >Prenota tavolo</router-link>
      
      
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
    img{
      height: auto;
      width: auto;
    }
  }
  

  .right-nav{
    width: 70%;
    background-color: #523333;
    .link{
      height: 100%;
      
      display: flex;
      justify-content: space-between;
      align-items: center;

    }
  }
}
.nav-mb-on{
  position: fixed;
  top: 0;
  left: 0;
  z-index: 10;
  background-color: $c-nav;
  width: 100%;
  height: 100%;
  transition: all .3s linear;
}
.burger-close-on{
  transition: all 1s linear 2s;
  position: absolute;
  top: 8%;
  right: 8%;
  opacity: 1;
  transition: display .3s linear;
  transition: opacity 1s linear 2s;
  .line{
    background-color: white;
    height: 30px;
    width: 5px;
    transform: rotateZ(45deg);
    position: absolute;
  }
  .l1{
    transform: rotateZ(135deg)
  }
}
.top-on{
  @include dfc;
  height: 100%;
  justify-content: space-around;
  flex-direction: column;
  padding: 10%;
  opacity: 1 ;
  transition: display .3s linear 1s;
  transition: opacity 5s linear 2s;
  .nav-link{

    text-transform: uppercase;
    line-height: 2rem;
    color: $c-nav-link;
    font-family: 'Gabarito', cursive;
    font-size: 1.8rem;
  }

}

.bottom-footer-on{
  display: none;
}
.nav-mb-off{
  position: fixed;
  top: 0;
  left: 0;
  z-index: 10;
  background-color: $c-nav;
  width: 100%;
  height: 0;
  transition: all .2s linear;


}
.burger-close-off{

  display: none;
  opacity: 0;
  transition: display .3s linear;
  transition: opacity 1s linear 2s;
  
}
.top-off{
  display: none;
  opacity: 0;
  transition: display .3s linear;
  transition: opacity 1s linear 2s;


}
.bottom-footer-off{
  display: none;
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


@media (max-width:1200px) {

  .t-mb{
    width: 30%;
    height: 200px;
    background-color: #523333;
    width: 25%;
    border-left: 0px solid transparent;
    border-right: 90px solid transparent;
    border-bottom: 200px solid white;
    -moz-transform:rotate(0);
    -webkit-transform:rotate(0);
    -ms-transform:rotate(0);
    -o-transform:rotate(0);
    transform:rotate(0);
    position: relative;
    z-index: 1;
  }
  .right-nav{
    background-color: white!important;
    .bg-mb{
      position: absolute;
      top: 0;
      right: 0;
      width: 50%;
      height: 200px;
      background-color: #523333;
    }
    .link{
      display: none!important;
    }
  }
}
@media (max-width:1100px) {
  .img{
    min-width: 400px;
  }
}


</style>


