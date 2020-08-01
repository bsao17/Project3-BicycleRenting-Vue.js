<template>
  <div id="container">
    
      <h1 class="card card-outlet-light"> {{title}} <span v-for="msg of msgs" :key="msg.id"> {{msg}} </span> </h1>
      
      

  </div>
</template>

<script> 
export default {
  data(){
    return{
      title: 'JCDecaux',
      msgs: [' - Location de vélo - ', ' Bike renting ']
    }
  }

}
</script>

<style scoped lang=scss>
$blueColor: black;
h1{
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  color: $blueColor;
  font-weight: bold;
  height: 10vh;
  margin-bottom: 20px;
}


</style>