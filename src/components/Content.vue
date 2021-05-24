<template>
  <div class="content" :class="cls">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "Content",
  props: {
    size: String,
  },
  computed: {
    cls() {
      const cls = {};

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
