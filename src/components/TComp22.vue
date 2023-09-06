<script lang="ts">
// eslint-disable-next-line @typescript-eslint/ban-ts-comment
// @ts-nocheck
import { defineComponent, h } from "vue";

import { store } from "./../store";

export default defineComponent({
  setup() {
    console.log("TComp22 setup");
    return {
      stuff: store.stuff,
    };
  },
  render() {
    console.log("render TComp22 start");
    const result = h(
      "div",
      { class: "TComp2" },
      this.stuff !== 2 ? [] : [h("div", { class: "p2" }, this.stuff.toString())]
    );
    console.log("render TComp22 done");

    return result;
  },
});
</script>

<style lang="postcss"></style>
