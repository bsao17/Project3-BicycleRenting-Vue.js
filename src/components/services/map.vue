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
                style="height: 600px; width: 100%"
                >
                <l-tile-layer
                    :url="url"
                />
                <l-marker :lat-lng="markerLatLng" ></l-marker>
                <l-marker
                v-for="marker of markers"
                :lat-lng="marker"
                :key="marker"

                ></l-marker>
                

                </l-map>
            </div>      
        </div>
    </div>
</template>





<script>

// import { latLng } from "leaflet";
import { LMap, LTileLayer, LMarker } from "vue2-leaflet";
import axios from 'axios'

export default {
    data(){
        return{
            city: null,
            apiKey: 'e56f43cd9e4a4aa5260f59360a683fa28aaa4e6b',
            reqData: [],
            markers: [],
            index:0,
            zoom: 12,
            center: [43.6043, 1.4437],
            url: 'https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
            markerLatLng: [43.6, 1.45]
        }
    },
    methods:{
        requestAjax:function(){
            const cityData = document.getElementById('city').value;
            this.city = cityData
            axios
            .get(`https://api.jcdecaux.com/vls/v1/stations?contract=${cityData}&apiKey=${this.apiKey}`)
            
            .then(response=>{
                this.reqData = response.data
                console.log(this.reqData)
                for(let e of this.reqData){
                    this.markers.push(e.position)
                }
                console.log(this.marker)
            });
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

