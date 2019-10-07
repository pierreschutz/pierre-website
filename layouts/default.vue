<template>
  <v-app dark>
    <v-content>
      <v-container>
        <v-parallax
          class="background-img"
          src="https://cdn.vuetifyjs.com/images/parallax/material.jpg"
        >
          <nuxt />
        </v-parallax>
      </v-container>
    </v-content>

    <v-footer :fixed="fixed" app>
      <span>&copy; Pierre Schutz 2019</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: "mdi-apps",
          title: "Welcome",
          to: "/"
        },
        {
          icon: "mdi-chart-bubble",
          title: "Inspire",
          to: "/inspire"
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Vuetify.js"
    };
  }
};
</script>

<style scoped>
.background-img {
  height: 100dpi;
}
</style>
