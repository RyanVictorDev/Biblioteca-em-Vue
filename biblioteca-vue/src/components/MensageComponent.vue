<template>
    <v-alert transition="scroll-x-reverse-transition" v-model="alert" width="30%" shaped dismissible color="error" border="left" elevation="2" colored-border icon="mdi-alert" class="ml-auto mt-auto">
      Você tem <strong>{{ qtdEmails }}</strong> livros não lidos.
    </v-alert>
</template>

<script>
export default{
    name: 'MensageComponent',

    components:{
        // 
    },

    data:() => ({
        qtdEmails: 55,
    })
}
</script>