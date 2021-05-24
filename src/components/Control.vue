<template>
  <div class="control" :class="cls">
    <slot></slot>
    <slot name="left-icon" class="is-left"></slot>
    <slot name="right-icon" class="is-right"></slot>
  </div>
</template>

<script>
export default {
  name: "Control",
  props: {
    isExpanded: Boolean,
  },
  computed: {
    cls() {
      const cls = {
        "has-icons-left": "left-icon" in this.$slots,
        "has-icons-right": "right-icon" in this.$slots,
        "is-expanded": this.isExpanded,
      };

      return cls;
    },
  },
};
</script>

<style></style>
