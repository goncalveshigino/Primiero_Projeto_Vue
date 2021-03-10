<template>

  <div id="app">

    <h3> Cadastro: </h3>
       <small id="nomeError" v-show="deuErro"> Nome invalido tente novamente</small><br>
        <input type="text" placeholder="nome" v-model="nomeField"><br>
        <input type="email" placeholder="email" v-model="emailField"><br>
        <input type="number" placeholder="idade" v-model="idadeField"><br>
        <button @click="cadastrarUsuario">Cadastrar</button>
        <hr>
        <div v-for="(cliente,index) in clientes" :key="cliente.id">

        <h4>{{index + 1}}</h4>

        <Cliente :cliente="cliente" @meDelete="deletarUsuario($event)"/>

    
        <h4>Edicao:</h4><br>

        <input type="text" v-model="cliente.nome">
        <input type="text" v-model="cliente.email">
      </div>
       
  </div>
  
</template>

<script>
import Cliente from './components/Cliente';
//import Produto from './components/Produto'

export default {

 name: 'App',
 data(){
   return {
    deuErro: false,
    nomeField: "",
    emailField: "",
    idadeField: 0,
      clientes: [
        {
          id:1,

          nome: "Gonçalves Higino",

          email: "gonza@gmail.com",

          idade: 23
        },
      
      ]
   }

 },
 components: {
   Cliente,
  // Produto
 },
 methods: {
     cadastrarUsuario: function(){
        
        if( this.nomeField == "" || this.nomeField == " " || this.nomeField.length < 4){
            this.deuErro = true;
        }else{
        this.clientes.push(
           {
              nome: this.nomeField,
              email: this.emailField,
              idade: this.idadeField,
              id: Date.now()
           }
        ),
       this.nomeField = "";
       this.emailField = "";
       this.idadeField = "";
       this.deuErro = false;
        }
     },
     deletarUsuario: function($event){
       console.log("Recebendo Evento!");
       var id =$event.idCliente;
       var novoArray = this.clientes.filter(cliente => cliente.id =! id);
       this.clientes = novoArray;
     }
 }

}

</script>

<style>
    #nomeError{
      color: red;
    }
</style>
