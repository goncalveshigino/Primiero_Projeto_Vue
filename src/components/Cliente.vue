<template>
   <div :class="{'cliente': !isPremium, 'cliente-premium': isPremium}">
       <!--input type="text" :value="nome"-->
       <!--input type="text" v-model="nome"-->
       <h4> Nome: {{cliente.nome}}</h4>
       <hr>
       <p>Email: {{cliente.email}}</p>
   
       <p v-if="showAge === true"> Idade: {{cliente.idade}}</p>
       <p v-else> O usuario escondeu a idade </p>

   </div>
</template>

<script>

export default {
   data(){
       return {
          isPremium: false
       }
   },

   props: {
      cliente: Object,
      showAge: Boolean
   }
}
</script>

<style scoped>

    .cliente {
        background-color: #ECE5E3;
        max-width: 600px;
        height: 150px;
        padding: 1%;
        margin-top: 2%;
    }

    .cliente-premium {
        background-color: black;
        color: yellow;
        max-width: 600px;
        height: 150;
        padding: 1%;
        margin-top:2%
    }

    
</style>
