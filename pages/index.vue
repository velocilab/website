<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card>
        <v-card-title class="headline">
          Welcome to Velocilab
        </v-card-title>
        <v-card-text>
          <p>We are a collective of lifetime learners, building cool stuff.</p>
          <div class="text-xs-right">
            <em><small>&mdash; <a href="https://thelackthereof.org/">Brock Wilcox (@awwaiid)</a></small></em>
          </div>
        </v-card-text>
      </v-card>
    </v-col>
    <v-col cols="12" sm="8" md="6">
      <v-card>
        <v-card-title class="headline">
          {{ page.title }}
        </v-card-title>
        <v-card-text>
          <nuxt-content :document="page" />
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  async asyncData ({ $content }) {
    const page = await $content('plane_game').fetch()
    return { page }
  }
}
</script>
