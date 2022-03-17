<template>
  <div class="about">
    <h1>You chose pokes</h1>
    <div v-if="pokes">
      <h2>{{ pokes.name }}</h2>
      <div class="pictures">
        <img :src="pokes.sprites.front_shiny" alt="" />
        <img :src="pokes.sprites.back_shiny" alt="" />
      </div>
      <h3>Types</h3>
      <div v-for="(type, index) in pokes.types" :key="index">
        <h3>{{ type.type.name }}</h3>
      </div>
    </div>
  </div>
</template>

<script>
import { useRoute } from 'vue-router';
import { reactive, toRefs } from 'vue';
export default {
  setup() {
    const route = useRoute();
    const state = reactive({
      pokes: null,
    });

    fetch(`https://pokeapi.co/api/v2/pokemon/${route.params.slug}/`)
      .then((res) => res.json())
      .then((data) => {
        state.pokes = data;
      });
    return { ...toRefs(state) };
  },
};
</script>
