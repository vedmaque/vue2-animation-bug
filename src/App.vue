<template>
  <div id="app">
    <TComp />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

import TComp from "./components/TComp.vue";

export default defineComponent({
  name: "App",
  components: {
    TComp,
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
