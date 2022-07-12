<template>
 <h1>Livros</h1>
 <div v-for="livro of livros" :key="livro.id">
 <h2>{{livro.titulo}} || {{livro.preco}}</h2>
 <h3>{{livro.categoria}} || {{livro.editora}}</h3>
 </div>
</template>

<script>
import axios from "axios";

export default {
  name: 'App',
  data(){
    return {
      livros: ''
    }
  },
  mounted () {
     axios({
            method:'get',
            url: 'http://127.0.0.1:8000/livros/',
            auth: {
                username: 'Raphael',
                password: 'gamemode'
            }
        }).then(response => this.livros = response.data);
  }
}
</script>

<style>

</style>
