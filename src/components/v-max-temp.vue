<template>
    <div class="vMaxTemp">
        <p class="title">Максимальная температура</p>
        <div class="container">
            <img 
                src="../assets/hot.svg" 
                alt="max temp"
                class="max-temp-icon"
            >
            <p class="value">{{ weatherInfo.maxTemp }}&deg;C</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'vMaxTemp',
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
.vMaxTemp{
    margin: 10px 0 0 10px;
    min-width: 435px;
    font-family: 'Montserrat', sans-serif;
    font-size: 20px;
    font-weight: 600;
    color: #00adb5;
    border: 1px solid #fff;
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
.max-temp-icon{
    width: 50px;
    height: 50px;
}
</style>