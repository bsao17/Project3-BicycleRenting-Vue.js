<template>
    <div>
        <button @click="requestAjax">request</button>
        <button @click="chooseCity">city choice</button>
        <select name="city" id="city">
            <option value="toulouse">Toulouse</option>
            <option value="lyon">Lyon</option>
            <option value="marseille">Marseille</option>
            <option value="nancy">Nancy</option>
            <option value="bruxelles">Bruxelles</option>
        </select>

        <div> {{results}} </div>


    </div>
</template>

<script>
export default {
    data(){
        return{
            results: '',
            cityChoice: '',
            toulouse: 'toulouse',
            bruxelles: 'bruxelles',
            nancy: 'nancy',
            marseille: 'marseille',
            lyon: 'lyon',
            luxembourg: 'luxembourg'
        }
    },
    methods:{
        requestAjax:function(){
            let cityData = document.getElementById('city');
            this.cityChoice = cityData.value;
            console.log(cityData.value);
            fetch(`https://api.jcdecaux.com/vls/v1/stations?contract=${this.cityChoice}&apiKey=e56f43cd9e4a4aa5260f59360a683fa28aaa4e6b`)
            .then(result => result.json())
            .then(response=>{
                this.results = response
            });
        }
    }

}
</script>

<style scoped lang="scss">
    
</style>

