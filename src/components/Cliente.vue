<template>
   <div :class="{'cliente': !isPremium, 'cliente-premium': isPremium}">

       <h4> Nome: {{cliente.nome |  processarNome}}</h4>
       <p>Email: {{cliente.email | processarEmail}}</p>
       <p v-if="showAge === true"> Idade: {{cliente.idade}}</p>
       <p v-else> O usuario escondeu a idade </p>
       <button @click="mudarCor($event)">Mudar cor!</button>
       <button @click="emitirEnventoDelete">Deletar</button><br>
       <hr>
       <hr>
       <h4>Id:{{ idEspecial }}</h4>
       
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
   },
   methods: {
       mudarCor: function($event){
           this.isPremium = !this.isPremium
       },
       emitirEnventoDelete: function(){
          console.log("Emitindo do Filho");
          this.$emit("meDelete", {idCliente: this.cliente.id,curso: "Formacao node.js", emPromocao: true, component: this});
       }
   },
   filters: {
       processarEmail: function(value){
          return value.toUpperCase();
       },
       processarNome: function(value){
          return "stack_code." +  value.toUpperCase();
       }
   },
   computed: {
       idEspecial: function(){
            return ( this.cliente.id  + this.cliente.email +  this.cliente.nome).toUpperCase();
       }
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
