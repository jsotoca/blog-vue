<template>
  <Titulo texto="Ruta con parametros" />
  <h2>Parametros: {{$route.params.id}}</h2>
</template>

<script>

import Titulo from '../components/Titulo.vue'

export default {
    name: 'Article',
    components: {
        Titulo
    }
}
</script>

<style>

</style>