<template>
  <v-app>
    <v-main>
      <div style="background-color: '#fff'">
        <v-toolbar color="indigo" dark>
          <v-app-bar-nav-icon></v-app-bar-nav-icon>
          <v-toolbar-title>NuxtJs Tutorial</v-toolbar-title>
          <v-spacer></v-spacer>
          <v-toolbar-items class="hidden-sm-and-down">
            <v-btn text><n-link to="/weather-app">Weather App</n-link></v-btn>
          </v-toolbar-items>
        </v-toolbar>
        <transition>
          <nuxt />
        </transition>
      </div>
    </v-main>
  </v-app>
</template>

<script>
export default {}
</script>

<style scoped>
a {
  text-decoration: none;
  color: white;
}
</style>
