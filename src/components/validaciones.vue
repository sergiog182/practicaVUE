<template>
    <div class="contenedor-componente">
        <p>
            <h1>
                Componente Validaciones
            </h1>
        </p>
        <div class="contenedor-principal">
            <form @submit.prevent="validarDatos">
				Nombres: <input type="text" id="nombres" class="campo-texto" v-model="nombres"/>
				<br>
				Apellidos: <input type="text" id="apellidos" class="campo-texto" v-model="apellidos"/>
				<br>
				Comentario:
				<br>
				<textarea v-model="comentario"></textarea>
				<br><font color="red" v-show="errorComentario" v-if="mensajeError != ''"><p> {{ mensajeError }} </p></font>
				<!-- v-bind se puede reemplazar por : -->
				<button type="submit" v-bind:disabled="!isFormValid()">Continuar</button>
			</form>
        </div>
    </div>
</template>

<script>
    export default {
        name: "suma", 
        data: function() {
            return {
                nombres: "",
                apellidos: "",
                comentario: "",
                errorComentario: false
            }
        },
        methods: {
            isFormValid: function() {
                return this.nombres != "" && this.apellidos != "";
            },
            validarDatos: function() {
                this.errorComentario = true
            }
        },
        computed: {
            mensajeError: function () {
                var val = this.comentario.trim();
                if (val == "") {
                    return "* Debes incluir un comentario";
                } else if (val.length < 5) {
                    return "* El comnetario debe ser mayor a 5 caracteres";
                } else if (val.length > 20) {
                    return "* El comnetario debe ser menor a 20 caracteres";
                }
                //return true;
                //return this.comentario.trim() == "" ? true : false;
            }
        }
    };
</script>