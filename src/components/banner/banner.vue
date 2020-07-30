<template>
  <div id="container">
    
      <h1 class="card"> {{title}} </h1>
      

  </div>
</template>

<script>
export default {
  data(){
    return{
      title:' welcome in devwebdino.com'
    }
  }

}
</script>

<style scoped lang=scss>
#container{
  display: flex;
  justify-content: center;
  align-items: center;
  width: 80vw;
  height: 80vh;
  margin: auto;
  border: solid black 1px;
  
}

</style>