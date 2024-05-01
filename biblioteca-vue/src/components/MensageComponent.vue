<template>
    <div>
        <v-list>
            <v-list-item v-for="mensage in mensages" :key="mensage.assunto" link>
                <v-alert transition="scroll-x-reverse-transition" v-model="alert" width="30%" shaped dismissible color="error" border="left" elevation="2" colored-border icon="mdi-alert" class="ml-auto mt-auto mb-2">
                    <strong>{{ mensage.qtdEmails }}</strong> {{ mensage.assunto }}
                </v-alert>
            </v-list-item>
        </v-list>


    </div>

</template>

<script>
export default{
    name: 'MensageComponent',

    components:{
        // 
    },

    data:() => ({
        qtdEmails: 55,
        mensages: [
            {assunto: 'Livros não lidos!', qtdEmails: 789},
            {assunto: 'Livros não lidos!', qtdEmails: 789},
            {assunto: 'Livros não lidos!', qtdEmails: 789}
        ]
    })
}
</script>