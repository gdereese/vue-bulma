<template>
  <span class="tag" :class="cls">
    <slot></slot>
  </span>
</template>

<script>
export default {
  name: "Tag",
  props: {
    color: String,
    isDelete: Boolean,
    isLight: Boolean,
    isRounded: Boolean,
    size: String,
  },
  computed: {
    cls() {
      const cls = {
        "is-delete": this.isDelete,
        "is-light": this.isLight,
        "is-rounded": this.isRounded,
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
