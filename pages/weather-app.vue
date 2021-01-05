<template>
  <v-container>
    <!--<v-layout>-->
    <v-flex xs12>
      <h1 class="display-1 text-center">Weather App</h1>
      <v-card color="blue-grey darken-2" dark>
        <v-card-text class="white--text"> Here is the card </v-card-text>
      </v-card>
    </v-flex>

    <v-flex xs12 class="mt-4">
      <v-text-field label="Another input" solo></v-text-field>
    </v-flex>
    <!--</v-layout>-->
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      city: 'London',
    }
  },
  created() {
    this.$axios
      .$get(
        `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&appid=54f640ee2778b99f51b719f876d3090b
`
      )
      .then((res) => console.log(res))
  },
}
</script>
