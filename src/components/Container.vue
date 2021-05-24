<template>
  <div class="container" :class="cls">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "Container",
  props: {
    isFluid: Boolean,
    maxWidth: String,
    width: String,
  },
  computed: {
    cls() {
      const cls = {
        "is-fluid": this.isFluid,
      };

      if (this.maxWidth) {
        const maxWidthClassName = `is-max-${this.maxWidth.toLowerCase()}`;
        cls[maxWidthClassName] = true;
      }
      if (this.width) {
        const widthClassName = `is-${this.width.toLowerCase()}`;
        cls[widthClassName] = true;
      }

      return cls;
    },
  },
};
</script>

<style></style>
