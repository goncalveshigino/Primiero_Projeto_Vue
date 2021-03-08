<template>
   <div id="cliente">
       <!--input type="text" :value="nome"-->
       <!--input type="text" v-model="nome"-->
       <h4> Nome: {{cliente.nome}}</h4>
       <hr>
       <p>Email: {{cliente.email}}</p>
         <hr>
       <p> Idade: {{cliente.idade}}</p>

   </div>
</template>

<script>

export default {
   data(){
       return {
          
       }
   },

   props: {
      nome: String,
      email: String,
      idade: Number,
      cliente: Object
   }
}
</script>

<style scoped>

    #cliente {
        background-color: #ECE5E3;
        max-width: 600px;
        height: 150px;
        padding: 1%;
        margin-top: 2%;
    }

    
</style>
