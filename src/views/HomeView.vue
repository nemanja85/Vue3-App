<template>
  <div class="home">
    <input type="text" placeholder="Enter Poke name" class="form-input" v-model="content" />
    <div class="pokes">
      <div v-for="(poke, index) in filteredList" :key="index">
        <router-link :to="`/about/${urlID[poke.name]}`">
          <span>{{ poke.name }}</span>
        </router-link>
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
        state.pokes = data.results;
        state.urlID = data.results.reduce((acc, val, index) => (acc = { ...acc, [val.name]: index + 1 }), {});
      });
    return { ...toRefs(state) };
  },
};
</script>
