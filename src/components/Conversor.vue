<template>
    <div class="row">
        <div class="col-8">
            <h1>🌡️ Conversor de Temperatura</h1>
        </div>
    </div>
    <div class="row">
        <div class="col-4">
            <h4>Ingrese Temperatura °C</h4>
            <input type="text" class="form-control" v-model.trim.number="tempC"></input>
        </div>
    </div>
    <div class="row">
        <div class="col-2">
            <p>Convertir Temperatura a °F:</p>
            <p>Convertir Temperatura a °K:</p>
        </div>
        
        <div class="col-1">
            <p :style="{color:setTxtColor(setTempF)}">{{ setTempF }}</p>
            <p :style="{color:setTxtColor(setTempK)}">{{ setTempK }}</p>
        </div>
    </div>
</template>


<script>
export default {
    name: 'Conversor',
    data() {
        return {
            tempC: null,
            txtColorF: '',
            txtColorK: '',
        }
    },
    computed: {
            setTempF() {
                return this.tempC * 2
            },
            setTempK() {
                return this.tempC * 10
            },
    },
    methods: {
        setTxtColor(temp){
                let color = 'red'
                if(temp<=0){
                    color = 'blue'
                    } else if(temp > 0 && temp < 15){
                        color ='magenta'
                        }
                return color
            }
        }
    }
</script>

<style scoped>
input, h4, p{
    margin-left: 15px;
    margin-bottom: 10px;
}
</style>