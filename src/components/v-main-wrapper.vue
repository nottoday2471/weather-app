<template>
    <div class="vMainWrapper">
        <v-select-city
            @selectCity="selectCity"
        />
        <div class="con1">
            <v-temp
                :weatherInfo="weatherInfo"
            />
            <div class="min-max-temps">
                <v-min-max-temp
                    :tempInfo="tempInfoForMin"
                />
                <v-min-max-temp
                    :tempInfo="tempInfoForMax"
                />
                <!-- <vMinTemp 
                    :weatherInfo="weatherInfo"
                />
                <vMaxTemp 
                    :weatherInfo="weatherInfo"
                /> -->
            </div>
        </div>
    </div>
</template>

<script>
import vTemp from './v-temp'
// import vMinTemp from './vMinTemp'
// import vMaxTemp from './vMaxTemp'
import vMinMaxTemp from './v-min-max-temp'
import vSelectCity from './v-select-city'

export default {
    name: 'vMainWrapper',
    components: {
        vTemp,
        // vMinTemp,
        // vMaxTemp,
        vMinMaxTemp,
        vSelectCity
    },
    data(){
        return{
            weatherInfo: {
                currTemp: '0_0',
                currTempFeelsLike: '0_0'
            },
            tempInfoForMin: {
                title: 'Минимальная температура',
                icon: 'cold.svg',
                temp: '0_0',
            },
            tempInfoForMax: {
                title: 'Максимальная температура',
                icon: 'hot.svg',
                temp: '0_0',
            },
            city: ''
        }
    },
    methods: {
        getWeatherInfo(){
            fetch(`http://api.openweathermap.org/data/2.5/weather?q=${this.city}&appid=d14f3b43c6e5ec98906d54c8b4696c38`)
            .then(res => res.json())
            .then(data => {
                console.log(data)
                // console.log(typeof +(data.main.temp - 273).toFixed(1))
                this.weatherInfo.currTemp = (data.main.temp - 273).toFixed(1)
                this.weatherInfo.currTempFeelsLike = (data.main.feels_like - 273).toFixed(1)
                this.tempInfoForMin.temp = (data.main.temp_min - 273).toFixed(1)
                this.tempInfoForMax.temp = (data.main.temp_max - 273).toFixed(1)
            })
            .catch(() => {})
        },
        selectCity(data){
            this.city = data
            this.getWeatherInfo()
            console.log(this.city)
        }
    },
    mounted(){
        //this.getWeatherInfo()
        //console.log(this.weatherInfo)
    }
}
</script>

<style scoped>
.vMainWrapper{
    /* position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 1200px;
    height: 500px; */
    /* border: 1px solid black; */
    margin: 30px 0 0 0;
    
}
.con1{
    display: flex;
    justify-content: space-around;
    margin: 60px 0 0 0;
}
.min-max-temps{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}
</style>
