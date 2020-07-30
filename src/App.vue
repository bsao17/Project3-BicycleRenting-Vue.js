<template>
  <div id="app">
    <h1 id="titleApp">hello</h1>
    <alert-box class="card bg-danger text-light">attention</alert-box>
    <banner></banner>
    
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import banner from './components/banner/banner.vue'

export default {
  name: 'App',
  components: {
    banner
   
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
#titleApp{
  display: flex;
  justify-content: center;
  align-items: center;
  color: red;
  border: solid red 1px;
  background-color: rgba(252, 61, 61, 1);
  width: 90vw;
  height: 100vh;
  position: absolute;
  top: 0%;
  left: 4.5%;
  
}
</style>
