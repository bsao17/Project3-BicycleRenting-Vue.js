<template>
  <div id="app">

    <div class="lign"></div>
    
    <carousel></carousel>

    <div class="lign"></div>

    <banner></banner>

    <div class="lign"></div>

    <section id="containerMap">

      <maped></maped>

    </section>

    <div class="lign"></div>

    <b-button class="btn-outline-light m-2" size='md' v-on:click="access">Reservation</b-button>
    
    
    <formular v-if="token"></formular>

    <div class="lign"></div>

    <card></card>
    
    
    
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import banner from './components/banner/banner.vue'
import card from './components/car/card.vue'
import carousel from './components/carousel/carousel.vue'
import formular from './components/formular/formular.vue'
import maped from './components/services/map.vue'

export default {
  name: 'App',
  data() {
    return{
      token: false
    }
  },
  methods:{
      access: function(){
        this.token=true
         event.stopPropagation()
        console.log(this.token)
      },
      foo: function(){
       
        console.log("j'ai cliqué")
        
      }
  },
  components: {
    banner,
    card ,
    carousel,
    formular,
    maped 
  
  }
}
</script>

<style>
#app {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  background-color: rgb(56, 56, 56);
  color: white;
}
.lign{
  width: 100%;
  height: 4px;
  background-color: black;
}
#containerMap{
  width: 90% ;
  height: 800px;
  border: outset rgb(168, 168, 168) 0.5rem;
  border-radius: 15px;
  margin: 20px;
  background-color: gray;
  overflow: auto;
}
</style>
