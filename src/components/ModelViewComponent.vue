<template>
    <div>
       <Header />
       <div>
            <v-container class="grey lighten-5">
                <h4>Models of {{this.brand}}</h4>
                <div class="grey lighten-5">
                    <span><router-link to="/">View Brands</router-link></span>
                </div>
            </v-container>
           <v-container class="grey lighten-5">
                <v-row>
                    <v-col v-for="model in models" :key="model.nome" cols="12" sm="4">
                        <ModelCard
                            v-bind:title="model.nome"
                            v-bind:codigo="model.codigo"
                        />
                    </v-col>
                </v-row>
            </v-container>
        </div> 
    </div>
</template>

<script>
import Header from './HeaderComponent';
import ModelCard from './ModelCardComponent';

import axios from 'axios';

export default {
    name: 'ListView',
    components: {
        Header,
        ModelCard
    },
    data() {
        return {
            id: this.$route.params.id,
            brand: this.$route.params.title,
            models: []
        }
    },
    created() {
        console.log('check', this.id)
        axios
        .get(`https://parallelum.com.br/fipe/api/v1/carros/marcas/${this.id}/modelos`)
        .then(response => {
            this.models = response.data.modelos
        })
        .catch(err => {
            console.log(err);
        })
    }
}
</script>.