<template>
  <v-app dark>
    <v-app-bar fixed app dense flat>
      <v-app-bar-nav-icon v-if="showNavIcon" @click="drawer = true"></v-app-bar-nav-icon>
      <v-toolbar-title>Kai Shoya</v-toolbar-title>
      <v-spacer />
      <span v-if="!showNavIcon">
        <v-btn v-for="item in items" :key="item.to" :to="item.to" nuxt text tile>{{ item.name }}</v-btn>
      </span>
      <v-btn icon href="https://twitter.com/shonari123" target="_blank">
        <v-icon>mdi-twitter</v-icon>
      </v-btn>
      <v-btn icon href="https://github.com/KaiShoya" target="_blank">
        <v-icon>mdi-github-circle</v-icon>
      </v-btn>
    </v-app-bar>
    <v-navigation-drawer v-model="drawer" absolute temporary>
      <v-list dense>
        <v-list-item-group active-class="text--accent-4">
          <v-list-item v-for="item in items" :key="item.to" :to="item.to" nuxt>
            <v-list-item-title>{{ item.name }}</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
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
export default {
  data () {
    return {
      drawer: false,
      items: [
        { to: '/', name: 'index' },
        { to: '/products', name: 'products' },
        { to: '/usable', name: 'usable' },
        { to: '/contact', name: 'contact' }
      ]
    }
  },
  computed: {
    showNavIcon: function () {
      return this.$vuetify.breakpoint.xs || this.$vuetify.breakpoint.sm
    }
  }
}
</script>
