<template>
  <div class="notification" :class="cls">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "Notification",
  props: {
    color: String,
    isLight: Boolean,
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

      return cls;
    },
  },
};
</script>

<style></style>
