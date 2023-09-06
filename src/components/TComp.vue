<template>
  <div class="TComp">
    <TComp1 key="1" />
    <TComp2 key="2" />

    <!-- <TComp1 key="1" v-if="comp2Ref" />
    <TComp2 key="2" ref="comp2Ref" /> -->
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

import TComp1 from "./TComp1.vue";
import TComp2 from "./TComp2.vue";

export default defineComponent({
  components: {
    TComp1,
    TComp2,
  },
  setup() {
    const comp2Ref = ref(null);

    console.log("TComp setup");
    return {
      comp2Ref,
    };
  },
});
</script>

<style lang="postcss">
:root {
  --vt-c-green: #42b883;
}
.button {
  font-size: 16px;
  border-radius: 8px;
  transition: background-color 0.5s, color 0.5s;
  position: relative;
  font-weight: 600;
  background-color: var(--vt-c-green);
  color: #fff;
  padding: 8px 1em 8px 1em;
  border-width: 0;
}

.flex {
  display: flex;
}
.p2 {
  padding: 16px;
}

.TComp {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  border: 1px solid black;
}

/* .TComp1 {
  border: 1px solid red;
}
.TComp2 {
  border: 1px solid blue;
} */

.item-transition {
  transition: all 0.2s;
}
</style>
