<template>
   <div id="cliente">
    <h2 id=cliente-nome>{{nome}}</h2>
    <h3> Descricao do cliente: {{descricao}}</h3>
    {{2*6+5}}
    <hr>
   </div>
</template>

<script>

export default {
   data(){
       return {
           nome:"Gonza Luiz",
           numero:" ",
           emai:"",
           idade:0,
           descricao:"Filho do tio Higino e da tia Nanda, gajo mau"
       }
   }
}
</script>

<style scoped>

    #cliente {
        max-width: 600px;
        height: 120px;
    }

    
</style>
