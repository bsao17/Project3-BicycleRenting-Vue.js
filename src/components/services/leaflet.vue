<template>

  <div >
    <l-map
      :zoom="zoom"
      :center="center"
      style="height: 500px; width: 100%"
    >
      <l-tile-layer
        :url="url"
        :attribution="attribution"
      />
      
    </l-map>


<!--ma props latitude longitude -->

    <p>Position des villes : {{lgt}} </p>


  </div>
</template>

<script>
import { latLng } from "leaflet";
import { LMap, LTileLayer,  } from "vue2-leaflet";

export default {
  name: "bikeRenting",
  components: {
    LMap,
    LTileLayer,
    // LMarker
  },
  data() {
    return {
      zoom: 12,
      center: latLng(43.6043, 1.4437),
      url: 'https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
      attribution: '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors'
    };
  },
  methods: {
    showAlert() {
      alert("Click!");
    }
  },
  props:['lgt', 'cityChoice']
};
</script>

<style>
.example-custom-control {
  background: #fff;
  padding: 0 0.5em;
  border: 1px solid #aaa;
  border-radius: 0.1em;
}
.custom-control-watermark {
  font-size: 200%;
  font-weight: bolder;
  color: #aaa;
  text-shadow: #555;
}
</style>
