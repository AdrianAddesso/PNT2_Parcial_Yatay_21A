<template>
    <div class="row">
        <div class="col-6">
            <h1>🌡️ Conversor de Temperatura</h1>
        </div>
    </div>
    <div class="row">
        <div class="col-6">
            <h4>Ingrese Temperatura °C</h4>
            <input type="number" class="form-control" v-model.trim.number="tempC" placeholder="0"></input>
        </div>
    </div>
    <div class="row">
        <div class="col-6">
            <p>👉 Convertir Temperatura a °F:
                <span :style="{color:setTxtColor(setTempF)}">{{ setTempF }}</span>
            </p>
            <p>👉 Convertir Temperatura a °K:
                <span :style="{color:setTxtColor(setTempK)}">{{ setTempK }}</span>
            </p>
        </div>
    </div>
</template>


<script>
export default {
    name: 'Conversor',
    data() {
        return {
            tempC: 0,
            txtColorF: '',
            txtColorK: '',
        }
    },
    computed: {
            setTempF() {
                return (this.tempC * 9/5) + 32
            },
            setTempK() {
                return this.tempC + 273.15
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