<template>
  <div class="level-item" :class="cls">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "LevelItem",
  props: {
    hasTextCentered: Boolean,
  },
  computed: {
    cls() {
      const cls = {
        "has-text-centered": this.hasTextCentered,
      };

      return cls;
    },
  },
};
</script>

<style></style>
