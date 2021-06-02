<template>
  <div id="app">


    <input placeholder="Nome" type="text" v-model="clienteAldo.nome"><br>
    <input placeholder="Idade" type="text" v-model="clienteAldo.idade"> <br>
    <input placeholder="Email" type="text" v-model="clienteAldo.email">



    <Cliente :cliente="clienteAldo" :showIdade="true" />
    <Cliente :cliente="clienteAldo" :showIdade="true" />
    <Cliente :cliente="clienteAldo" :showIdade="false" />
    <Cliente :cliente="clienteAldo" :showIdade="false" />
    
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
      clientes:[
        { 
        
        nome:"Aldo",
        email: "aldo@gmail.com",
        idade: 22

        },
        {
        nome:"João",
        email: "jao@gmail.com",
        idade: 21

        },
        {
        nome:"Marcos",
        email: "marcos@gmail.com",
        idade: 23

        }
      ],
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
