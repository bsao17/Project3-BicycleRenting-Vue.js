<template>
  <div id="app">

    <carousel></carousel>

    <banner></banner>

    <b-button class="btn-outline-primary m-2" size='md' v-on:click="access">Entrer</b-button>
    <input type="text" placeholder="Enter Password" v-if="token" >
    
    <card></card>
    
    
  </div>

  
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import banner from './components/banner/banner.vue'
import card from './components/car/card.vue'
import carousel from './components/carousel/carousel.vue'

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
    carousel 
  
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
  background-color: rgb(82, 82, 82);
  color: white;
}
</style>
