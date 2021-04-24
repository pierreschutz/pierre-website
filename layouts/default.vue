<template>
  <v-app dark class="app">

    <!-- Left navigation drawer with links to other pages -->
    <v-navigation-drawer
      v-model="drawer"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <!-- Top app bar with links -->
    <v-app-bar
      color="rgba(0, 0, 0, 0.8)"
      :clipped-left="clipped"
      fixed
      dense
      app
      class="app-bar"
    >

      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />

      <!-- Home button -->
      <v-btn
        icon
        href="/"
      >
        <v-icon>mdi-home</v-icon>
      </v-btn>


      <!-- Bar title-->
      <v-toolbar-title v-text="title"/>

      <v-spacer/>

      <!-- LinkedIn Button -->
      <v-btn icon
             href="https://linkedin.com/in/pierreschutz"
             target="_blank"
      >
        <v-icon>mdi-linkedin</v-icon>
      </v-btn>


      <!-- GitHub Button -->
      <v-btn icon
             href="https://github.com/pierreschutz"
             target="_blank"
      >
        <v-icon>mdi-github</v-icon>
      </v-btn>

    </v-app-bar>

    <!-- Page content -->
      <v-content>
        <v-container>
          <nuxt/>
        </v-container>
      </v-content>

    <!-- Copyright footer -->
    <v-footer :fixed="fixed" app color="rgba(0, 0, 0, 0.8)">
      <span>{{copyright}}</span>
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
          },
          {
            icon: "mdi-earth",
            title: "My World Map",
            to: "/map"
          }
        ],
        right: true,
        rightDrawer: false,
        title: "My Awesome Portfolio (Pierre Schutz)",
        copyright: "© Pierre Schutz 2021"


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

  .app-bar {
    border-bottom-left-radius: 5px;
    border-bottom-right-radius: 5px;
  }

  .app {
    background-image: url("static/background_night_1.svg");
    background-size: 250% auto;
    background-repeat: no-repeat;
    background-position-x: center;

  }

</style>
