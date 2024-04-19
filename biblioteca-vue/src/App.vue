<template>
  <v-app>
    <v-main>
    <NavBarComponent />
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>
import NavBarComponent from './components/NavBarComponent.vue';

export default {
  name: 'App',

  components: {
    NavBarComponent
  }
};
</script>
