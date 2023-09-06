<template>
  <div class="TComp2">
    <div v-if="stuff === 2" class="p2">{{ stuff }}</div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

import { store } from "./../store";

export default defineComponent({
  setup() {
    console.log("TComp2 setup");

    return {
      stuff: store.stuff,
    };
  },
});
</script>

<style lang="postcss"></style>
