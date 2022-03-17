<template>
  <div class="home">
    <h2>Poke API</h2>
  </div>
</template>

<script>
// @ is an alias to /src
import { reactive } from 'vue';

export default {
  name: 'HomeView',
  setup() {
    const state = reactive({
      poke: [],
      urlID: {},
    });

    fetch('https://pokeapi.co/api/v2/pokemon?offset=0')
      .then((res) => res.json())
      .then((data) => {
        console.log(data);
        state.poke = data.results;
        state.urlID = data.results.reduce((acc, val, index) => {
          acc = { ...acc, [val.name]: index + 1 };
        });
      });
  },
};
</script>
