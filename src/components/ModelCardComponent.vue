<template>
  <div>
    <v-card
        class="mx-auto"
        max-width="344"
    >
        <v-card-text>
        <div><h3>Model Name: {{title}}</h3></div>
        <div>Code: {{codigo}}</div>
        </v-card-text>
    </v-card>
  </div>
</template>
<script>
export default {
    name: 'modelCard',
    props: {
        title: String,
        codigo: String
    }
}
</script>