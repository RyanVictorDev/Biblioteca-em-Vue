<template>
  <v-app id="inspire">
    <NavComponent/>
    <v-main>
      <router-view/>
    </v-main>
    <mensage-component/>
  </v-app>
</template>

<script>
import MensageComponent from './components/MensageComponent.vue';
import NavComponent from './components/NavComponent.vue';

export default {
  name: 'App',

  components: {
    NavComponent,
    MensageComponent
  },

  data: () => ({
    // 
  }),

};
</script>

<style scoped>

</style>
