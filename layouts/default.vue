<template>
  <v-app dark style="background-color: antiquewhite">
    <v-content>


      <v-container >
        <nuxt/>
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
    height: 1000px;
  }

  html {
    --color-blue-light: #88bdbc;
    --color-blue-medium: #254e58;
    --color-blue-dark: #112d32;
    --color-gray-dark: #4f4a41;
    --color-gray-light: #6e6658;
  }

</style>
