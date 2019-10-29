<template>
<div>
<h1>{{titulo}}</h1>
  <ul>
    <li v-for='foto of fotos'>
      <img :src='foto.url' :alt='foto.titulo'>
    </li>
  </ul>
</div>
</template>

<script>
export default {
  data () {
    
    return {
      titulo: 'Alurapic',
      fotos: []
    }
  },

  created() {
    
    this.$http.get('http://localhost:3000/v1/fotos') /*realiza requisição http para API*/
    .then(res => res.json()) /*converte o resultado para json*/
    .then(foto => this.fotos = foto); /*atribui o resultado para o objeto fotos[]*/
  }
}
</script>

<style>


</style>
