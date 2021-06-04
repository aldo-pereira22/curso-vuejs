<template>
  <div id="app">

    <div class="buttons">
      <button class="button is-primary">Primary</button>
      <button class="button is-link">Link</button>
    </div>

        <h3>Cadastro:</h3>
        <small id="nomeErro" v-show="deuErro"> O nome é inválido: Tente novamente</small> <br>
        <input type="text" placeholder="nome" v-model="nomeField" name="" id=""> <br><br>
        <input type="email" placeholder="email" v-model="emailField"  name="" id=""> <br><br>
        <input type="number" placeholder="idade" v-model="idadeField" ><br><br>
        <button @click="cadastrarUsuario"> Cadastrar</button>

    <hr>

 
 

    <div v-for=" (cliente, index) in orderClientes" :key="cliente.id">
      <h4> {{ index + 1 }} </h4>
       <Cliente :cliente="cliente" @delete="deleteUsuario($event)" /> 
       <hr>
    </div>  


  
  </div>
</template>

<script>
import _ from 'lodash';
  import Cliente from './components/Cliente'




export default {
  name: 'App',
  data(){
    return{
      deuErro: false,
      nomeField:"",
      emailField:"",
      idadeField: 0,
      
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
      if(this.nomeField == "" || this.nomeField.length < 3){
        this.deuErro = true;

      }else {

      this.clientes.push({nome: this.nomeField, email: this.emailField, idade:this.idadeField, id:Date.now})
      this.nomeField = "";
      this.emailField = "";
      this.idade = 0;
      this.deuErro = false;

      }
    },

    deleteUsuario: function($event){
        
        var id = $event.idCliente;
        var novoArray = this.clientes.filter(cliente => cliente.id != id);
        this.clientes = novoArray;
    }
  }, 
  computed: {
    orderClientes: function (){
      return _.orderBy(this.clientes, ['nome'], ['asc'])
    }
  }
}
</script>

<style>

  #nomeErro {
    color: red;
  }

</style>
