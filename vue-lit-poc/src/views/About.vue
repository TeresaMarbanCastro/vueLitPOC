<template>
  <div>
    <about-view></about-view>
    <div v-for="pokemon in pokemonList">
      <a :href="'/detail/' + pokemon.name">{{pokemon.name}}</a>
    </div>
  </div>
</template>
<script>
import axios from "axios";
import '../components/about-view';
import Detail from './Detail.vue';

export default {
  name: 'about',
  components: {
    Detail
  },
  data() {
    return {
      pokemonList: []
    }
  },
  created() {
    this.fetchData();
  },
  methods: {
    fetchData() {
      axios.get("https://pokeapi.co/api/v2/pokemon/?limit=811").then(response => {
        this.pokemonList = response.data.results;
      });
    },
    redirectToDetail() {
      console.log('Redirect to detail');
      router.push("detail")
    }
  }
}
</script>



