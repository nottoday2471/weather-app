<template>
    <div class="vLogo">
        <p class="logo-title">WeatherApp</p>
    </div>
</template>

<script>

export default {
    name: 'vLogo'
}
</script>

<style scoped>
.vLogo{
    display: flex;
    background: #00adb5;
}
.logo-title{
    color: #eeeeee;
    font-family: 'Montserrat', sans-serif;
    font-size: 42px;
    font-weight: 600;
    padding: 15px 0 15px 15px;
    margin: 0;
    /* top: 0;
    left: 50%;
    transform: translateX(-50%); */
}
</style>
