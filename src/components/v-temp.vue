<template>
    <div class="vTemp">
        <p class="title">Текущая температура</p>
        <p class="value">{{ weatherInfo.currTemp }}&deg;C</p>
        <p class="title">Чувствуется как</p>
        <p class="value">{{ weatherInfo.currTempFeelsLike }}&deg;C</p>
    </div>
</template>

<script>


export default {
    name: 'vTemp',
    components: {
        
    },
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
.vTemp{
    margin: 10px 0 0 10px;
    min-width: 350px;
    font-family: 'Montserrat', sans-serif;
    font-size: 20px;
    font-weight: 600;
    color: #00adb5;
    border: 1px solid #fff;
    background-color: #393e46;
    display: inline-block;
    //border-radius: 20px;
    height: 350px;
    /* position: relative; */
    box-shadow: 0 0 10px silver;
    transition: box-shadow .5s ease;
}
.vTemp:hover{
    box-shadow: 0 0 35px silver;
}
.title{
    padding: 20px;
    margin: 0;
    font-size: 26px;
    text-align: center;
}
.value{
    color: #eeeeee;
    text-align: center;
    font-size: 58px;
    padding: 0 15px 5px 15px;
    margin: 0;
    /* display: inline-block; */
    text-align: center;
    /* position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%); */
}
.value2{
    color: #eeeeee;
    text-align: center;
    font-size: 58px;
    padding: 0 15px 5px 15px;
    margin: 0;
    /* display: inline-block; */
    text-align: center;
    /* position: absolute;
    left: 50%;
    bottom: 0;
    transform: translate(-50%, 0); */
}
</style>