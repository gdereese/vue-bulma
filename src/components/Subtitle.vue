<template>
  <div class="subtitle" :class="cls" v-is="el">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "Subtitle",
  props: {
    el: {
      default: "div",
      type: String,
    },
    isSpaced: Boolean,
    size: Number,
  },
  computed: {
    cls() {
      const cls = {
        "is-spaced": this.isSpaced,
      };

      if (this.size) {
        const sizeClassName = `is-${this.size}`;
        cls[sizeClassName] = true;
      }

      return cls;
    },
  },
};
</script>

<style></style>
