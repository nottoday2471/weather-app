<template>
    <div class="vMinMaxTemp">
        <p class="title">{{ tempInfo.title }}</p>
        <div class="container">
            <img 
                :src="require('../assets/' + tempInfo.icon)"
                alt="temp"
                class="temp-icon"
            >
            <p class="value">{{ tempInfo.temp }}&deg;C</p>
        </div>
    </div>
</template>

<script>

export default {
    name: 'vMinMaxTemp',
    props: {
        tempInfo: {
            type: Object,
            default(){
                return {}
            }
        }
    },
}
</script>

<style scoped>
.vMinMaxTemp{
    margin: 10px 0 0 10px;
    min-width: 435px;
    font-family: 'Montserrat', sans-serif;
    font-size: 20px;
    font-weight: 600;
    color: #00adb5;
    border: 1px solid #fff;
    background-color: #393e46;
    display: inline-block;
    //border-radius: 20px;
    box-shadow: 0 0 10px silver;
    transition: box-shadow .5s ease;
}
.vMinMaxTemp:hover{
    box-shadow: 0 0 35px silver;
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
.temp-icon{
    width: 50px;
    height: 50px;
}
</style>
