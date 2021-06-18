<template>
  <div class="home">
    <Titulo texto="Mi página principal" />
  </div>
</template>

<script>
import Titulo from '../components/Titulo.vue'

export default {
  name: 'Home',
  components: {
    Titulo    
  }
}
</script>
