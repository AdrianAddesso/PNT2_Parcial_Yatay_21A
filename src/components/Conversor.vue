<template>
    <div class="row">
        <div class="col-8">
            <h1>Conversor de Temperatura</h1>
        </div>
    </div>
    <div class="row">
        <div class="col-4">
            <h4>Ingrese Temperatura °C</h4>
            <input type="text" class="form-control" v-model.trim.number="tempC"></input>
        </div>
    </div>
    <div class="row">
        <div class="col-4">
            <p>Convertir Temperatura a °F: {{ setTempF }}</p>
            <p>Convertir Temperatura a °K: {{ setTempK }}</p>
        </div>
    </div>
</template>


<script>
export default {
    name: 'Conversor',
    data() {
        return {
            tempC: 1,
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
    }
    }
</script>

<style scoped>
input, h4, #card-container,.alert{
    margin-left: 15px;
    margin-bottom: 15px;
}

h1 {
    margin-left: 15px;
    margin-bottom: 35px
}
</style>