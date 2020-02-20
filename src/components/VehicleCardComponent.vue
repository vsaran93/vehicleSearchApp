<template>
  <v-card
    class="mx-auto"
    max-width="344"
  >
    <v-card-text>
      <div><h3>Brand: {{title}}</h3></div>
      <div>Code: {{codigo}}</div>
      <div>
        <span><router-link v-bind:to="'/models/'+ codigo+'/'+ title">View Models</router-link></span>
      </div>
    </v-card-text>
  </v-card>
</template>
<script>
export default {
    name: 'vehicleCard',
    props: {
        title: String,
        codigo: String
    }
}
</script>