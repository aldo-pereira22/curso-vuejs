<template>
    <div :class="{'cliente' : !isPremium, 'cliente-premium':isPremium  }">

        <h4>Nome : {{cliente.nome}} </h4>        
        <hr>
            <p v-if="showIdade === true" > Idade: {{cliente.idade}} </p>
            <p v-else> Usuário escondeu a idade</p>
        <hr>
        Numero: {{numero}}
        <hr>
        email: {{cliente.email}}

    </div>

</template>

<script>
    export default {
        data(){
            return {
                isPremium: false
            }
        },
        props:{
            cliente: Object,
            showIdade: Boolean
        }
}

</script>

<style scoped>

    .cliente {
        background-color: #ececec;
        max-width: 600px;
        padding: 30px;
        margin: 4px; 
    }

    .cliente-premium{
        background-color: black;
        color: yellow;

    }

</style>