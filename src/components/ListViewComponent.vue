<template>
    <div>
       <Header />
       <div>
           <v-container class="grey lighten-5">
                <v-row>
                    <v-col v-for="vehicle in vehicles" :key="vehicle.nome" cols="12" sm="4">
                        <VehicleCard
                            v-bind:title="vehicle.nome"
                            v-bind:codigo="vehicle.codigo"
                        />
                    </v-col>
                </v-row>
            </v-container>
        </div> 
    </div>
</template>

<script>
import Header from './HeaderComponent';
import VehicleCard from './VehicleCardComponent';

import axios from 'axios';

export default {
    name: 'ListView',
    components: {
        Header,
        VehicleCard
    },
    data() {
        return {
            vehicles: []
        }
    },
    created() {
        axios
        .get(`https://parallelum.com.br/fipe/api/v1/carros/marcas`)
        .then(response => {
            this.vehicles = response.data
        })
        .catch(err => {
            console.log(err);
        })
    }
}
</script>.