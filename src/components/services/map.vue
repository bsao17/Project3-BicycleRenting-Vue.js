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

        <div id="map">
            
           
            
        </div>
        

           



    </div>
</template>





<script>



export default {
    data(){
        return{
            city: null,
            results: [],
            index: 0
            
        }
    },
    methods:{
        requestAjax:function(){
            const cityData = document.getElementById('city').value;
            this.city = cityData
            console.log(this.city, this.results);
            fetch(`https://api.jcdecaux.com/vls/v1/stations?contract=${cityData}&apiKey=e56f43cd9e4a4aa5260f59360a683fa28aaa4e6b`)
            .then(result => result.json())
            .then(response=>{
                for(let i of response){
                    this.results.push(i.position)
                }
            });
        }
    },
    components:{
       
    }
}
</script>




<style scoped lang="scss">

   
</style>

