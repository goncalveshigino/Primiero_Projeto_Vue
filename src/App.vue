<template>

  <div id="app">
      <input type="text" v-model="clienteHigino.nome">
      <Cliente :cliente="clienteHigino"/>  
      <Cliente :cliente="clienteHigino"/>  
      <Cliente :cliente="clienteHigino"/>  
      <Cliente :cliente="clienteHigino"/>   
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
      }
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
