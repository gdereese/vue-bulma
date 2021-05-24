<template>
  <span class="icon" :class="cls"><slot></slot></span>
</template>

<script>
export default {
  name: "Icon",
  props: {
    color: String,
    size: String,
  },
  computed: {
    cls() {
      const cls = {};

      if (this.color) {
        const colorClassName = `has-text-${this.color.toLowerCase()}`;
        cls[colorClassName] = true;
      }
      if (this.size) {
        const sizeClassName = `is-${this.size.toLowerCase()}`;
        cls[sizeClassName] = true;
      }

      return cls;
    },
  },
};
</script>

<style></style>
