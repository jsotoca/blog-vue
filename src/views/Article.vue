<template>
  <Titulo texto="Ruta con parametros" />
  <h2>Parametros: {{$route.params.id}}</h2>
  <div v-if="article.id">
    <h3>{{article.title}}</h3>
    <p>{{article.body}}</p>
  </div>
  <div v-else>
    <p>cargando articulo...</p>
  </div>
</template>

<script>

import Titulo from '../components/Titulo.vue'

export default {
    name: 'Article',
    data() {
      return {
        id: String,
        article: {}
      }
    },
    components: {
        Titulo
    },
    methods:{
      async obtenerArticulo(){
        try {
          this.id = this.$route.params.id;
          const data = await fetch(`https://jsonplaceholder.typicode.com/posts/${this.id}`);
          this.article = await data.json();
          console.log(this.article);
        } catch (error) {
          console.log(error);
        }
      }
    },
    created() {
      this.obtenerArticulo();
    }
}
</script>

<style>

</style>