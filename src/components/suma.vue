<template>
    <div class="contenedor-componente">
        <p>
            <h1>
                Componente Suma
            </h1>
        </p>
        <div class="contenedor-principal">
            Primero: <input type="number" id="primero" class="campo-texto" v-model="primero"/>
            <br>
            Segundo: <input type="number" id="segundo" class="campo-texto" v-model="segundo"/>
            <br>
            Total: {{ total }}
        </div>
    </div>
</template>

<script>
    export default {
        name: "suma", 
        data: function() {
            return {
                primero: 0,
		        segundo: 0
            }
        },
        computed:{
            total: function() {
                return parseInt(this.primero) + parseInt(this.segundo);
            }
        }
    };
</script>