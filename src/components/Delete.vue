<template>
  <button class="delete" :class="cls"></button>
</template>

<script>
export default {
  name: "Delete",
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
