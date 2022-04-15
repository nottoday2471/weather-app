<template>
  <div id="app">
    <!-- <img
      src="./assets/background-day.png"
      alt="background"
      class="background"
      v-if="isDay"
    >
    <img
      src="./assets/background-night.png"
      alt="background"
      class="background"
      v-else
    > -->
    <v-logo />
    <v-main-wrapper />
  </div>
</template>

<script>
import vLogo from './components/v-logo'
import vMainWrapper from './components/v-main-wrapper'

export default {
  name: 'App',
  components: {
    vMainWrapper,
    vLogo
  },
  data(){
    return{
      isDay: true,
    }
  },
  methods: {
    isDayCheck(){
      let date = new Date()
      if(
        (date.getHours() >= 21 && date.getHours() <= 24) 
        || (date.getHours() >= 0 && date.getHours() <= 8)
        ){
        this.isDay = false
      } else{ 
        this.isDay = true
      }
    }
  },
  created(){
    this.intervalId = setInterval(() => this.isDayCheck(), 1000)
  },
  beforeDestroy() {
    if(this.intervalId){
      clearInterval(this.intervalId)
    }
  }
}
</script>

<style scoped>
.background{
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  
}
</style>
