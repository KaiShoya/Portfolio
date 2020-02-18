<template>
  <v-app dark>
    <v-app-bar fixed app>
      <v-spacer />
      <v-btn icon href="https://twitter.com/shonari123" target="_blank">
        <v-icon>mdi-twitter</v-icon>
      </v-btn>
      <v-btn icon href="https://github.com/KaiShoya" target="_blank">
        <v-icon>mdi-github-circle</v-icon>
      </v-btn>
    </v-app-bar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {}
</script>
