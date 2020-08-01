<template>
  
  <div id="container">
  <b-carousel
    id="carousel-fade"
    style="text-shadow: 0px 0px 2px #000"
    fade
    indicators
    img-width="1024"
    img-height="480"
  >
    <b-carousel-slide
      caption="First slide"
      img-src="../../assets/accueil.jpeg"
    ></b-carousel-slide>

    <b-carousel-slide
      caption="Second Slide"
      img-src="../../assets/img5.jpeg"
    ></b-carousel-slide>
    
    <b-carousel-slide
      caption="Third Slide"
      img-src="../../assets/img7.jpg"
    ></b-carousel-slide>

    <b-carousel-slide
      caption="Fourth Slide"
      img-src="../../assets/img8.jpg"
    ></b-carousel-slide>

  </b-carousel>
</div>


</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>

$sizeCarousel: 70%;

#container{
    width: $sizeCarousel;
    height: 50%;
    overflow: auto;
    margin: 20px 0px;
    border: outset grey 0.5rem;
    border-radius: 15px;
}

</style> 


