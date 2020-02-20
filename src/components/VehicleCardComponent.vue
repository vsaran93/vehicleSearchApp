<template>
  <v-card
    class="mx-auto"
    max-width="344"
  >
    <v-card-text>
      <div><h3>{{title}}</h3></div>
      <div>Vehicle Code: {{codigo}}</div>
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