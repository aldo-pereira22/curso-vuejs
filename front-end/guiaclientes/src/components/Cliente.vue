<template>
    <div id="cliente">

        <h4>Nome : {{cliente.nome}} </h4>        
        <hr>
            Idade: {{cliente.idade}}
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

            }
        },
        props:{
            nome:String,
            email:String,
            idade: Number,
            cliente:Object
        }
    }

</script>

<style scoped>

    #cliente {
        background-color: #ececec;
        max-width: 600px;
        padding: 30px;
        margin: 4px; 
    }

</style>