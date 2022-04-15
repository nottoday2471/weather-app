<template>
    <div class="vMinTemp">
        <p class="title">Минимальная температура</p>
        <div class="container">
            <img 
                src="../assets/cold.svg" 
                alt="min temp"
                class="min-temp-icon"
            >
            <p class="value">{{ weatherInfo.minTemp }}&deg;C</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'vMinTemp',
    props: {
        weatherInfo: {
            type: Object,
            default(){
                return {}
            }
        }
    }
}
</script>

<style scoped>
.vMinTemp{
    margin: 10px 0 0 10px;
    min-width: 435px;
    font-family: 'Montserrat', sans-serif;
    font-size: 20px;
    font-weight: 600;
    color: #00adb5;
    border: 1x solid #fff;
    background-color: #393e46;
    box-shadow: 0 0 75px silver;
    display: inline-block;
    border-radius: 20px;
}
.title{
    padding: 20px;
    margin: 0;
    font-size: 26px;
}
.container{
    display: flex;
    justify-content: center;
}
.value{
    color: #eeeeee;
    text-align: center;
    font-size: 40px;
    padding: 0 15px 5px 15px;
    margin: 0;
}
.min-temp-icon{
    width: 50px;
    height: 50px;
}
</style>