<template>
  <v-app id="inspire">
    <NavComponent/>
    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>
import NavComponent from './components/NavComponent.vue';

export default {
  name: 'App',

  components: {
    NavComponent,
  },

  data: () => ({
    // 
  }),

};
</script>

<style scoped>

</style>
