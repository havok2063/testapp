<template>
  <v-app>
    <v-navigation-drawer app v-model='drawer' dark>

      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="title">
            Navigation
          </v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item v-for="item in items" :key="item.title" link>
          <v-list-item-content>
            <v-list-item-title>{{item.title}}</v-list-item-title>
          </v-list-item-content>          
        </v-list-item>
      </v-list>

    </v-navigation-drawer>

    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        <v-tooltip bottom>
          <template v-slot:activator="{ on }">
            <v-app-bar-nav-icon v-on="on" @click.stop="drawer = !drawer" />
          </template>
          <span>Toggle Navigation Drawer</span>
        </v-tooltip>

        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Latest Release</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-content>
      <HelloWorld/>
    </v-content>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';

export default {
  name: 'App',

  components: {
    HelloWorld,
  },

  data: () => ({
    // template data goes here
    drawer: null,
    items: [{title: 'Stuff'}, {title:'Goes'}, {title:'Here'}]
  }),
};
</script>
