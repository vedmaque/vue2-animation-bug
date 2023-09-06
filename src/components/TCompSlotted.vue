<script lang="ts">
import { defineComponent, h } from "vue";

export default defineComponent({
  setup() {
    console.log("TCompSlotted setup");
  },
  render() {
    console.log("render TCompSlotted start");
    const r = h("div", undefined, this.$slots.default);
    console.log("render TCompSlotted done");
    return r;
  },
});
</script>
