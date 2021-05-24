<template>
  <figure class="image" :class="cls">
    <slot></slot>
  </figure>
</template>

<script>
export default {
  name: "ImageContainer",
  props: {
    isFullwidth: Boolean,
    sizeRatio: String,
    squareSize: Number,
  },
  computed: {
    cls() {
      const cls = {
        "is-fullwidth": this.isFullwidth,
      };

      if (this.sizeRatio) {
        const sizeRatioClassName = `is-${this.sizeRatio}`;
        cls[sizeRatioClassName] = true;
      }
      if (this.squareSize) {
        const sizeClassName = `is-${this.squareSize}x${this.squareSize}`;
        cls[sizeClassName] = true;
      }

      return cls;
    },
  },
};
</script>

<style></style>
