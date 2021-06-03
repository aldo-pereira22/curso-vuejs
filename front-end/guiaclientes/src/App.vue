<template>
  <div id="app">


        <h3>Cadastro:</h3>
        <input type="text" placeholder="nome" v-model="nomeField" name="" id=""> <br><br>
        <input type="email" placeholder="email" v-model="emailField"  name="" id=""> <br><br>
        <input type="number" placeholder="idade" v-model="idadeField" ><br><br>
        <button @click="cadastrarUsuario"> Cadastrar</button>

    <hr>

 
 

    <div v-for=" (cliente, index) in clientes" :key="cliente.id">
      <h4> {{ index + 1 }} </h4>
       <Cliente :cliente="cliente" /> 
       <hr>
    </div>  


  
  </div>
</template>

<script>
  import Cliente from './components/Cliente'



export default {
  name: 'App',
  data(){
    return{
      nomeField:"",
      emailField:"",
      idadeFiled: 0,
      
      clientes:[
        { 
        id: 2,
        nome:"Aldo",
        email: "aldo@gmail.com",
        idade: 22

        }
      ]

    }
  },
  components: {
    Cliente
    
  },
  methods:{
    cadastrarUsuario:function(){
      this.clientes.push({nome: this.nomeField, email: this.emailField, idade: this.idadeFiled, id:Date.now})
      this.nomeField = "";
      this.emailField = "";
      this.idade = "";
    }
  }
}
</script>

<style>

</style>
