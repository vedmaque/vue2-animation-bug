<script lang="ts">
// eslint-disable-next-line @typescript-eslint/ban-ts-comment
// @ts-nocheck
import { defineComponent, onBeforeUpdate, onUpdated, h } from "vue";

// import TCompSlotted from "./TCompSlotted.vue";
// import TCompAlt from "./TCompAlt.vue";
// import TCompHack1 from "./TCompHack1.vue";

import { store } from "./../store";

export default defineComponent({
  setup() {
    console.log("TComp11 setup");
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
      console.log("TComp11 onUpdated");
    });

    onBeforeUpdate(() => {
      console.log("TComp11 onBeforeUpdate");
    });

    return { stuff, toggle };
  },
  render() {
    console.log("render TComp11 start");
    const result = h("div", { class: "TComp1" }, [
      h("div", { class: "p2" }, [
        h("button", { class: "button", on: { click: this.toggle } }, "Click"),
      ]),
      // h(TCompAlt),
      // h(TCompSlotted, undefined, [h("div", "TCompSlotted slot content")]),
      h(
        "transition-group",
        {
          props: {
            tag: "div",
            name: "animation",
          },
          class: "flex",
        },
        [
          h(
            "div",
            { class: "item-transition", key: "somekey" },
            "Animation Bug"
          ),
        ]
      ),
      this.stuff !== 1
        ? []
        : [h("div", { class: "p2" }, this.stuff.toString())],
    ]);
    console.log("render TComp11 done");

    return result;
  },
});
</script>
