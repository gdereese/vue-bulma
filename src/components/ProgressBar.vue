<template>
  <progress class="progress" :max="max" :value="value">
    {{ value ? `${(value / max) * 100}%` : null }}
  </progress>
</template>

<script>
export default {
  name: "ProgressBar",
  props: {
    color: String,
    max: Number,
    size: String,
    value: Number,
  },
  computed: {
    cls() {
      const cls = {
        "is-light": this.isLight,
      };

      if (this.color) {
        const colorClassName = `is-${this.color.toLowerCase()}`;
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
