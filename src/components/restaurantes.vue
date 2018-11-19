<template>
    <div class="contenedor-componente">
        <h1>
            Componente Restaurantes
        </h1>
        <div class="contenedor-principal">
            <ul>
				<li :key="index" v-for="(restaurant, index) in restaurants">
					{{ restaurant }}
					<button type="button" @click="eliminatRestaruante(index)"> - </button>
				</li>
			</ul>
			<input type="text" v-model="newRestaurant" @keyup.enter="addRestaruant"/> &nbsp;
			<button type="button" @click="addRestaruant">Agregar restaruante</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: "restaurantes", 
        data: function() {
            return {
                restaurants: [
                    "Italiano",
                    "Mexicano",
                    "Mediterraneo"
                ],
                newRestaurant: ''
            }
        },
        methods: {
            addRestaruant: function(value) {
                if (this.newRestaurant.trim() != '') {
                    this.restaurants.push(this.newRestaurant);
                    this.newRestaurant = '';
                } else {
                    alert("nombre del restaurante es obligatorio");
                }
            },
            eliminatRestaruante: function(value) {
                this.restaurants.splice(value, 1);
            }
        }
    };
</script>