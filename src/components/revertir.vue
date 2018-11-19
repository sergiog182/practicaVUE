<template>
    <div class="contenedor-componente">
        <p>
            <h1>
                Componente Revertir
            </h1>
        </p>
        <div class="contenedor-principal">
            <div class="contenedor-secundario">
                <p> bienvenido, {{ name }} </p>
            </div>
            <div class="contenedor-secundario">
                <p>Datos almacenados en el VM:</p>
                <pre>
                    {{ $data }}
                </pre>
            </div>
            <div class="contenedor-secundario">
                <input type="text" v-model="name" class="campo-texto"/> 
                &nbsp;
                <button type="button" class="boton" v-on:click="revertir">Invertir</button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "revertir", 
        data: function() {
            return {
                name: "Sergio"
            }
        },
        methods: {
            revertir: function() {
                this.name = this.name.split('').reverse().join('')
            }
        }
    };
</script>
