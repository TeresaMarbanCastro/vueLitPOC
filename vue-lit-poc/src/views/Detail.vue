
<template>
  <div abel>
    <img :src="pokemonDetail.sprites.front_default"/>
  </div>
</template>
<script>
import axios from "axios";

export default {
  data() {
    return {
      pokemonDetail: {}
    }
  },
  created() {
    this.fetchData();
  },
  methods: {
    fetchData() {
      axios.get("https://pokeapi.co/api/v2/pokemon/" + this.$route.params.id).then(response => {
        this.pokemonDetail = response.data;
      });
    }
  }
}
</script>


