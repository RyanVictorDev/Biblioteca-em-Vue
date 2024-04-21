<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app dark>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            OnLibrary <v-icon>mdi-book</v-icon>
          </v-list-item-title>
          <v-list-item-subtitle>
            Menu
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item v-for="item in items" :key="item.title" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app dark>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title><v-icon>mdi-book</v-icon> OnLibrary</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>
// import NavBarComponent from './components/NavBarComponent.vue';

export default {
  name: 'App',

  components: {
    // NavBarComponent
  },

  data: () => ({
    drawer: null,
    items: [
          { title: 'Home', icon: 'mdi-home' },
          { title: 'Galeria', icon: 'mdi-book' },
          { title: 'Sobre', icon: 'mdi-help-box' },
        ],
    right: null,
  }),

};
</script>
