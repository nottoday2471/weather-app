<template>
    <div class="vSelectCity">
        <vue-picker v-model="citySelected" placeholder="Ваш любимый город">
            <!-- <vue-picker-option value="">Ваш любимый город</vue-picker-option> -->
            <vue-picker-option value="Kiev">
                <span>Kiev</span>
            </vue-picker-option>
            <vue-picker-option value="London">
                <span>London</span>
            </vue-picker-option>
            <vue-picker-option value="Moscow">
                <span>Moscow</span>
            </vue-picker-option>
            <vue-picker-option value="Rome">
                <span>Rome</span>
            </vue-picker-option>
            <vue-picker-option value="Warsaw">
                <span>Warsaw</span>
            </vue-picker-option>
        </vue-picker>
        <p 
            v-if="citySelected !== ''"
            class="citySelected"
        >
            {{ citySelected }}
        </p>
        <p 
            v-else
            class="citySelected"
        >
            Ваш город
        </p>
        <button 
            @click="selectCity"
            class="button"
        >
            Показать погоду
        </button>
        <!-- <select 
            name="select-city" 
            v-model="citySelected"
        >
            <option value="" disabled>Ваш любимый город</option>
            <option value="Kiev">Kiev</option>
            <option value="London">London</option>
        </select>
        <button @click="selectCity">Показать погоду</button> -->
    </div>
</template>

<script>
import {VuePicker, VuePickerOption} from '@invisiburu/vue-picker'
import '@invisiburu/vue-picker/dist/vue-picker.min.css'

export default {
    name: 'vSelectCity',
    components: {
        VuePicker,
        VuePickerOption
    },
    data(){
        return {
            citySelected: ''
        }
    },
    methods: {
        selectCity(){
            this.$emit('selectCity', this.citySelected)
        }
    }
}
</script>

<style scoped>
.vSelectCity{
    display: flex;
    justify-content: space-around;
}
span{
    font-size: 24px;
}
.button{
    background: #393e46;
    box-shadow: 0 0 10px silver;
    transition: box-shadow .5s ease;
    font-size: 24px;
    color: #eeee;
    width: 300px;
}
.button:hover{
    box-shadow: 0 0 35px silver;
}
.citySelected{
    margin: 0;
    padding: 0;
    font-size: 32px;
    color: #eeee;
    font-weight: 600;
    display: inline-block;
    min-width: 300px;
    text-align: center;
}
</style>