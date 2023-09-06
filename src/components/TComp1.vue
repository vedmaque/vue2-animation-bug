<template>
  <div class="TComp1">
    <div class="p2">
      <button class="button" @click="toggle">Click</button>
    </div>
    <!-- <TCompAlt /> -->

    <!-- <TCompSlotted>
      <div>TCompSlotted slot content</div>
    </TCompSlotted> -->

    <transition-group name="animation" tag="div" class="flex">
      <div class="item-transition" key="somekey">Animation Bug</div>
    </transition-group>

    <!-- <TCompHack1 /> -->

    <div v-if="stuff === 1" class="p2 inner">
      {{ stuff }}
    </div>

    <!-- <div v-if="stuff === 2" class="p2 inner">
      {{ stuff }}
    </div> -->
  </div>
</template>

<script lang="ts">
import { defineComponent, onBeforeUpdate, onUpdated } from "vue";

// import TCompAlt from './TCompAlt.vue';
// import TCompSlotted from './TCompSlotted.vue';
// import TCompHack1 from "./TCompHack1.vue";

import { store } from "./../store";

export default defineComponent({
  components: {
    // TCompAlt,
    // TCompSlotted,
    // TCompHack1,
  },
  setup() {
    console.log("TComp1 setup");
    const stuff = store.stuff;

    function toggle() {
      if (stuff.value === 1) {
        console.log("changing 1 -> 2");
        store.stuff.value = 2;
      } else if (stuff.value === 2) {
        console.log("changing 2 -> 1");
        store.stuff.value = 1;
      }
    }

    onUpdated(() => {
      console.log("TComp1 onUpdated");
    });
    onBeforeUpdate(() => {
      console.log("TComp1 onBeforeUpdate");
    });

    return { stuff, toggle };
  },
});
</script>
