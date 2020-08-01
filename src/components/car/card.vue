<template>

<div id="container">
  <b-card id="imgJcd"
    overlay
    img-src="https://www.lerevenu.com/sites/site/files/styles/img_lg/public/field/image/jcdecaux-carte-l-grassin_0.jpg?itok=h4QXO9s_"
    img-alt="Card Image"
    text-variant="white"
    title="Concept application by devwebdino.com"
  >
  
    <b-card-text>
      <a href="mailto:contact@devwebdino.com"> m@il: {{mail}} </a>
    </b-card-text>
  </b-card>

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
  height: 150px;
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

