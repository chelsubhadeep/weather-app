<template>
  <v-container>
    <!--<v-layout>-->
    <v-flex xs12>
      <h1 class="display-1 text-center">Weather App</h1>
      <v-card color="blue-grey darken-2" dark>
        <v-card-text class="white--text">
          <v-layout justify-center>
            <v-flex class="text-center">
              <h4>Temperature</h4>
              <h1 class="display-1">{{ weather.name }}</h1>
              <img :src="icon" alt="weather icon" />
            </v-flex>
          </v-layout>
        </v-card-text>
      </v-card>
    </v-flex>

    <v-flex xs12 class="mt-4">
      <v-form @submit.prevent="getWeatherInfo">
        <v-text-field
          v-model="city"
          label="Enter City Name"
          solo
        ></v-text-field>
      </v-form>
    </v-flex>

    <!--</v-layout>-->
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      city: 'London',
      weather: {},
    }
  },
  computed: {
    icon() {
      return this.weather.weather
        ? `https://openweathermap.org/img/w/${this.weather.weather[0].icon}.png`
        : ``
    },
  },
  created() {
    this.getWeatherInfo()
  },
  methods: {
    getWeatherInfo() {
      this.$axios
        .$get(
          `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&appid=54f640ee2778b99f51b719f876d3090b
	`
        )
        .then((res) => (this.weather = res))
    },
  },
}
</script>
