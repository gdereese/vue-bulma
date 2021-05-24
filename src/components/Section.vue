<template>
  <section class="section" :class="cls">
    <slot></slot>
  </section>
</template>

<script>
export default {
  name: "Section",
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
