<template>
  <v-app>
    <v-app-bar
      color="deep-purple accent-4"
      dark
      prominent
      app
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Dictionary</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-filter</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>

     <v-navigation-drawer
      v-model="drawer"
      absolute
      bottom
      temporary
      app
    >
      <v-list
        nav
        dense
      >
        <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
          <v-list-item>
            <v-list-item-title>Preklad</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-title>Prihlásenie</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-title>O projekte</v-list-item-title>
          </v-list-item>

        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

  <!-- Sizes your content based upon application components -->
  <v-main>

    <!-- Provides the application the proper gutter -->
    <v-container fluid>
    <HelloWorld/>
    </v-container>
  </v-main>

  <v-footer app>
    <!-- -->
  </v-footer>
</v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';
// import Navbar from './components/Navbar';

export default {
  name: 'App',

  components: {
    HelloWorld,
    // Navbar
  },

  data: () => ({
    drawer: false,
      group: null,
  }),
  watch: {
      group () {
        this.drawer = false
      },
    },
};
</script>
