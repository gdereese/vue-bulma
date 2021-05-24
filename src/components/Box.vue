<template>
  <div class="box" v-is="el">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "Box",
  props: {
    el: {
      default: "div",
      type: String,
    },
  },
};
</script>

<style></style>
