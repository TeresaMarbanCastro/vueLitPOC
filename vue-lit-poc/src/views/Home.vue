<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <Frontal msg="Welcome to Pokemon Searcher"/>
  </div>
</template>

<script>
// @ is an alias to /src
import Frontal from '@/components/Frontal.vue'

export default {
  name: 'home',
  components: {
    Frontal
  }
}
</script>
