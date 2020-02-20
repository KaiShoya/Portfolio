<template>
  <v-layout justify-space-around align-center wrap>
    <v-flex v-for="card in cards" :key="card.title" xs12 sm6 md4 class="pa-1">
      <v-card>
        <v-card-title v-text="card.title"></v-card-title>
        <v-card-text v-text="card.text"></v-card-text>

        <v-card-actions>
          <v-layout justify-space-around>
            <v-btn :to="`/products/${card.id}`" nuxt block text>
              詳細
            </v-btn>
          </v-layout>
        </v-card-actions>

        <v-card-actions>
          <v-layout justify-space-around>
            <v-btn
              v-if="card.githubLink"
              :href="`https://github.com/KaiShoya/${card.githubLink}`"
              target="_blank"
              icon
            >
              <v-icon>mdi-github-circle</v-icon>
            </v-btn>

            <v-btn v-if="card.src" :href="card.src" target="_blank" icon>
              <v-icon>mdi-open-in-new</v-icon>
            </v-btn>
          </v-layout>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
import products from '@/assets/products.json'

export default {
  data () {
    return {
      cards: products
    }
  }
}
</script>
