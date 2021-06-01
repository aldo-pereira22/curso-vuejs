<template>
  <div id="app">


    <input placeholder="Nome" type="text" v-model="clienteAldo.nome"><br>
    <input placeholder="Idade" type="text" v-model="clienteAldo.idade"> <br>
    <input placeholder="Email" type="text" v-model="clienteAldo.email">



    <Cliente :cliente="clienteAldo" />

    <Cliente :cliente="clienteAldo" />
    <Cliente :cliente="clienteAldo" />
    <Cliente nome="Maria" email="maria@gmail" idade="40" />
    
  </div>
</template>

<script>
  import Cliente from './components/Cliente'


export default {
  name: 'App',
  data(){
    return{
      nomeAldo:"Aldo Pereira",
      clienteAldo: {
        nome:"Aldo",
        email: "aldo@gmail.com",
        idade: 30
      },
      clienteJoao: {
        nome:"João",
        email: "João@gmail.com",
        idade: 20

      }
    }
  },
  components: {
    Cliente
    
  }
}
</script>

<style>

</style>
