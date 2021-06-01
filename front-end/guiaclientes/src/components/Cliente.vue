<template>
    <div id="cliente">
        
        <!-- <input type="text" :value="nome" name="" id="">  usado para referenciar uma variável dentro do campos de textos-->

        <input type="text" :value="descricao">
        <h2>Cliente :{{ nome }} </h2>   
        <h3>Descrição do Cliente: <p> {{descricao}} </p> </h3> 
        {{ 2 + 2 * 4 }}
    </div>

</template>

<script>
    export default {
        data(){
            return {
                nome: "Aldo",
                numero: "",
                email: "",
                iddade: "",
                descricao: "lorem IPSUM E TAL"
            }
        }
    }

</script>

<style scoped>
  
</style>