<template>
  <div>
    <v-carousel cycle hide-delimiter-background show-arrows-on-hover>
    <v-carousel-item v-for="(slide, i) in slides" :key="i">
      <v-sheet class="fill-height" :color="colors[i]" height="100%">
        <v-row class="d-flex my-auto" justify="center">
          <div fixed centered>
            {{ slide }}
          </div>
        </v-row>
      </v-sheet>
    </v-carousel-item>       
  </v-carousel>
  </div>
</template>

<script>
  export default {
    name: 'HelloWorld',
    
    components:{
      // 
    },

    data:() => ({
        colors: [
          'error',
          'warning',
          'pink darken-2',
          'red lighten-1',
          'deep-purple accent-4',
        ],
        slides: [
          'First',
          'Second',
          'Third',
          'Fourth',
          'Fifth',
        ],
      }
    ),
  }
</script>

