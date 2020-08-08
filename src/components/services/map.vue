<template>
    <div id="container">
        <section class="container">

            <select class="card card-outline-primary" name="city" id="city">
                <option value="toulouse">Toulouse</option>
                <option value="lyon">Lyon</option>
                <option value="marseille">Marseille</option>
                <option value="nancy">Nancy</option>
                <option value="bruxelles">Bruxelles</option>
                <option value="luxembourg">Luxembourg</option>
                <option value="brisbane">Brisbane</option>
                <option value="creteil">Créteil</option>
                <option value="cergy-pontoise">Cergy-Pontoise</option>
                <option value="amiens">Amiens</option>
            </select>

            <button class="btn btn-primary text-light" id="buttonChoice" @click="requestAjax">request</button>

        </section>

        <!-- map-->

        <div id="map">

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

                <l-marker
                :marker=markerMap
                ></l-marker>

            </div>
                    
        </div>
        

           



    </div>
</template>





<script>

import { latLng } from "leaflet";
import { LMap, LTileLayer, LMarker } from "vue2-leaflet";

export default {
    data(){
        return{
            city: null,
            results: [],
            index: 0,
            zoom: 12,
            center: latLng(43.6043, 1.4437),
            url: 'https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
            attribution: '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors',
            markerLat: [],
            markerLng: [],
            markerMap: latLng(this.results)
        }
    },
    methods:{
        requestAjax:function(){
            const cityData = document.getElementById('city').value;
            this.city = cityData
            
            fetch(`https://api.jcdecaux.com/vls/v1/stations?contract=${cityData}&apiKey=e56f43cd9e4a4aa5260f59360a683fa28aaa4e6b`)
            .then(result => result.json())
            .then(response=>{
                for(let i of response){
                    this.results.push(i.position.lat, i.position.lng)
                    this.markerLat.push(i.position.lat)
                    this.markerLng.push(i.position.lng)
                }
            });
            console.log(this.results)
        }
    },
    components:{
        LMap,
        LTileLayer,
        LMarker
    }
}
</script>




<style scoped lang="scss">

   
</style>

