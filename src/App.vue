<template>
 <h1>Livros</h1>
 <div v-for="livro of livros" :key="livro.id" class=" container mx-auto p-4  border w-40">
 <div class="text-2xl semibold">{{livro.titulo}}</div> 
 <div>{{livro.preco}}</div>
 <div>{{livro.categoria.descricao}}</div>
 <div>{{livro.editora.nome}}</div>
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
