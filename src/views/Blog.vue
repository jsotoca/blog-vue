<template>
  <div class="blog">
    <Titulo texto="Titulo de mi blog" />
    <!-- <button @click="consumirApi">Consumir api</button> -->
    <div v-if="articles">
      <div v-for="article in articles" :key="article.id">
        <router-link :to="`/article/${article.id}`" > {{article.title}} </router-link>
        
      </div>
    </div>
  </div>
</template>

<script>

import Titulo from '../components/Titulo.vue';

export default {
  data() {
    return {
      articles: []
    }
  },
  components: {
    Titulo
  },
  methods:{
    async consumirApi(){
      try {
        const data = await fetch('https://jsonplaceholder.typicode.com/posts');
        this.articles = await data.json();
      } catch (error) {
        console.log(error);
      }
    }
  },
  created () {
    this.consumirApi();
  }
}
</script>

<style>

</style>