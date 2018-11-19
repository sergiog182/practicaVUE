<template>
    <div class="contenedor-componente">
        <h1>
            Componente Bienvenido
        </h1>
        <div class="contenedor-principal">
            <div id="formulario" v-if="!formSubmitted">
                <!-- v-on se puede reemplazar por @ -->
                <form v-on:submit.prevent="validarDatos">
                    Primer Nombre: <input type="text" id="first_name" class="campo-texto" v-model="first_name"/>
                    <br>
                    Apellido: <input type="text" id="last_name" class="campo-texto" v-model="last_name"/>
                    <br>
                    <!-- v-bind se puede reemplazar por : -->
                    <button type="submit" v-bind:disabled="!isFormValid()">Continuar</button>
                </form>
            </div>
            <div id="mensaje"  v-else>
                Bienvenido {{ first_name }} {{ last_name }}
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "bienvenido", 
        data: function() {
            return {
                first_name: "",
                last_name: "",
                formSubmitted: false
            }
        },
        methods: {
            isFormValid: function() {
                return this.first_name != "" && this.last_name != "";
            },
            validarDatos: function() {
                this.formSubmitted = true;
            }
    	}
    };
</script>