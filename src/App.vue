<template>

  <div id="app">
      <input type="text" v-model="clienteHigino.nome">
      <input type="text" v-model="clienteHigino.email">

    

      <div v-for="(cliente,index) in clientes" :key="cliente.id">
        <h4>{{index + 1}}</h4>
        <Cliente :cliente="cliente"/>
        <hr>
        <h4> Edicao: </h4> 

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
      nomeDoHigino: "Gonçalves Luís Higino",

      clienteHigino: {

        nome: "Gonçalves Higino",

        email: "gonza@gmail.com",

        idade: 23
      },
      clientes: [
        {
          id:1,

          nome: "Gonçalves Higino",

          email: "gonza@gmail.com",

          idade: 23
        },
        {
          id:2,
             
          nome: "Hino Higino",

          email: "hino@gmail.com",

          idade: 22
        },
        {
          id:3,

          nome: "Luiz Higino",

          email: "luiz@gmail.com",

          idade: 20
        },
         {
          id:4,

          nome: "Silvio Higino",

          email: "silvio@gmail.com",

          idade: 30
        }
      ]
   }

 },
 components: {
   Cliente,
  // Produto
 }

}

</script>

<style>

</style>
