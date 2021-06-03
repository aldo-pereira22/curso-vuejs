<template>
    <div :class="{'cliente' : !isPremium, 'cliente-premium':isPremium  }">
        <h4>Nome : {{cliente.nome}} </h4>        
        <hr>

            <p> email: {{cliente.email}} </p>
            <p>  Idade: {{cliente.idade}} </p>
<!--        <button   @click="mudarCor($event)"   >Mudar a cor</button> -->
            <button @click="emitirEventoDelete"> Deletar </button>
  

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
        },
        methods:{
            mudarCor: function($event){
                console.log($event.type);
  
                this.isPremium = !this.isPremium;
            },
            emitirEventoDelete: function(){
                alert("PASSANDO O EVENTO"  )
                this.$emit("delete", {idCliente: this.cliente.id ,curso:"Formação em node:  ", emPromocao: true, componente: this})

            },
            testar: function(){
                alert("Testando para valer")
            }
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