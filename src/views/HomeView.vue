<template>
  <div class="home">
    <h2>Poke API</h2>
    <input type="text" placeholder="Enter Poke name" class="form-input" v-model="content" />
    <div class="pokes">
      <div v-for="(poke, index) in filteredList" :key="index">
        <span>{{ poke.name }}</span>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import { computed, reactive, toRefs } from 'vue';

export default {
  name: 'HomeView',
  setup() {
    const state = reactive({
      pokes: [],
      urlID: {},
      content: '',
      filteredList: computed(() => updatePokes()),
    });

    function updatePokes() {
      return !state.content ? [] : state.pokes.filter((poke) => poke.name.includes(state.content));
    }

    fetch('https://pokeapi.co/api/v2/pokemon?offset=0')
      .then((res) => res.json())
      .then((data) => {
        console.log(data);
        state.pokes = data.results;
        state.urlID = data.results.reduce((acc, val, index) => {
          acc = { ...acc, [val.name]: index + 1 };
        });
      });
    return { ...toRefs(state) };
  },
};
</script>
