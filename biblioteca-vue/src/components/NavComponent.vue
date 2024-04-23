<template>
    <div>
        <v-navigation-drawer v-model="drawer" app dark v-bind:mini-variant="miniVariant" color="#333">
        <v-list>
          <v-list-item class="px-2">
            <v-list-item-avatar>
              <v-img src="https://randomuser.me/api/portraits/women/75.jpg"></v-img>
            </v-list-item-avatar>
          </v-list-item>

          <v-list-item link>
            <v-list-item-content>
              <v-list-item-title class="text-h6">
                Your Profile :)
              </v-list-item-title>
              <v-list-item-subtitle>yourcoolemail@gmail.com</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list flat nav>
          <v-list-item-group v-model="selectedItem" color="primary">
            <v-list-item v-for="item in items" :key="item.title" link>
              <v-list-item-icon>
                <v-icon>{{ item.icon }}</v-icon>
              </v-list-item-icon>

              <v-list-item-content>
                <v-list-item-title>{{ item.title }}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list-item-group>
        </v-list>

        <template v-slot:append>
          <v-list dense nav class="rounded-xl mb-5 mx-auto">
            <v-list-item link class="redBack">
                <v-list-item-icon>
                <v-icon>mdi-account</v-icon>
              </v-list-item-icon>

              <v-list-item-content>
                <v-list-item-title>Logout</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>
        </template>

    </v-navigation-drawer>

    <v-app-bar dense app dark color="#333">
      <v-app-bar-nav-icon @click="miniVariant = !miniVariant; btnShow = !btnShow;" ></v-app-bar-nav-icon>
      <v-toolbar-title><v-icon>mdi-book</v-icon> OnLibrary</v-toolbar-title>
    </v-app-bar>
    </div>
</template>

<script>
export default{
    name: 'NavComponent',

    components:{
        // 
    },

    data:() => ({
        miniVariant: true,
        btnShow: true,
  
        items: [
            { title: 'Home', icon: 'mdi-home', para: '/' },
            { title: 'Galeria', icon: 'mdi-book', para: '/'},
            { title: 'Sobre', icon: 'mdi-help-box', para:'/about' },
            ],
        right: null,
    }),
}
</script>

<style scoped>
    .redBack{
        background-color: rgb(255, 52, 52);
    }
</style>