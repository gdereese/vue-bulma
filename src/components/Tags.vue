<template>
  <div class="tags" :class="cls">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "Tags",
  props: {
    hasAddons: Boolean,
    size: String,
  },
  computed: {
    cls() {
      const cls = {
        "has-addons": this.hasAddons,
      };

      if (this.size) {
        const sizeClassName = `are-${this.size.toLowerCase()}`;
        cls[sizeClassName] = true;
      }

      return cls;
    },
  },
};
</script>

<style></style>
