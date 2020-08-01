<template>

<div id="container">
  <a href="https://devwebdino.com">
  <b-card id="imgJcd"
    overlay
    img-src="../../assets/bannerDwd.jpeg"
    img-alt="Card Image"
    text-variant="white"
  >
  
  </b-card></a>

</div>

  
</template>

<script>


export default {
  data(){
    return{
      mail: 'contact@devwebdino.com'
    }
  },
  components:{
    
  }

}
</script>

<style scoped>
#container{
  background-color: cadetblue;
  width: 30%;
  height: auto;
  box-sizing: border-box;
  overflow: auto;
  margin: 15px;
}
a{
  color: whitesmoke;
}
a:visited{
  color: whitesmoke;
}
#imgJcd{
  opacity: 0.8;
}

</style>>

