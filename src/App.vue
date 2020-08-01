<template>
  <div id="app">

    <carousel></carousel>

    <banner></banner>

    <div id="lign"></div>

    <section id="containerMap">


    </section>

    <b-button class="btn-outline-light m-2" size='md' v-on:click="access">Entrer</b-button>
    <input type="text" placeholder="Enter First Name" v-if="token" >
    <input type="text" placeholder="Enter Last Name" v-if="token" >
    
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
  background-color: rgb(56, 56, 56);
  color: white;
}
#lign{
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
}
</style>
