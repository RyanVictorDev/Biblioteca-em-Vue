<template>
    <div>
        <v-navigation-drawer v-model="drawer" app dark v-bind:mini-variant="miniVariant" color="#333">
        <v-list>
          <v-list-item class="px-2">
            <v-list-item-avatar v-if="log == true">
              <v-img src="https://randomuser.me/api/portraits/women/75.jpg"></v-img>
            </v-list-item-avatar>

            <v-list-item-avatar v-if="log == false">
              <v-img src="https://randomuser.me/api/portraits/lego/6.jpg"></v-img>
            </v-list-item-avatar>
          </v-list-item>

          <v-list-item link>
            <v-list-item-content v-if="log == true">
              <v-list-item-title class="text-h6">
                Your Profile :)
              </v-list-item-title>
              <v-list-item-subtitle>yourcoolemail@gmail.com</v-list-item-subtitle>
            </v-list-item-content>

            <v-list-item-content v-if="log == false">
              <v-list-item-title class="text-h6">
                Undefined user
              </v-list-item-title>
              <v-list-item-subtitle class="red--text">Não registrado!</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list flat nav>
          <v-list-item-group v-model="selectedItem" color="primary">
            <v-list-item v-for="item in items" :key="item.title" :to="item.to" link>
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
          <!-- ação de Click adicionado temporariamente, feito para fins de testes! -->
          <v-list v-if="log == true" dense nav class="rounded-xl mb-5 mx-auto" @click="log = !log">
            <v-list-item link class="error">
                <v-list-item-icon>
                <v-icon>mdi-account</v-icon>
              </v-list-item-icon>

              <v-list-item-content>
                <v-list-item-title>Logout</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>

          <v-list v-if="log == false" dense nav class="rounded-xl mb-5 mx-auto" @click="log = !log">
            <v-list-item link class="primary">
                <v-list-item-icon>
                <v-icon>mdi-account</v-icon>
              </v-list-item-icon>

              <v-list-item-content>
                <v-list-item-title>Login</v-list-item-title>
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
        log: false,
  
        items: [
            { title: 'Home', icon: 'mdi-home', to: '/' },
            { title: 'Biblioteca', icon: 'mdi-book', to: '/biblioteca'},
            { title: 'Sobre', icon: 'mdi-help-box', to:'/about' },
            ],
        right: null,
    }),
}
</script>

<style scoped>
/*  */
</style>