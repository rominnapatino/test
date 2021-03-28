<template>
  <v-app>
    <v-app-bar
      fixed
      app
      class="d-flex justify-center" 
    >
      <v-toolbar-title v-text="title" />
      <v-spacer />
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer
      :absolute="!fixed"
      app
      class="d-flex justify-center" 
    >
    <p>Desarrollado por <a href="https://wordpress.rominna.online">Rominna Patiño</a> <span> &copy; {{ new Date().getFullYear() }}</span></p>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      fixed: false,
      title: 'Criptomonedas'
    }
  }
}
</script>
