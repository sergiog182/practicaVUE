<template>
    <div class="contenedor-componente">
        <h1>
            Componente Experiencia
        </h1>
        <div class="contenedor-principal">
            A&ntilde;os de experiencia: <input type="number" v-model="experienceYears" disabled/> 
			&nbsp; <button type="button" @click="addYear">+</button>
			&nbsp; <button type="button" @click="takeYear" :disabled="experienceYears == 0">-</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: "experiencia", 
        data: function() {
            return {
                experienceYears: 0
            }
        },
        methods:{
            addYear: function() {
                this.experienceYears++
            },
            takeYear: function () {
                this.experienceYears--
            }
        }
    };
</script>