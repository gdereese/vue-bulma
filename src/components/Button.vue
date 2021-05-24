<template>
  <button class="button" :class="cls" :disabled="isDisabled">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    color: String,
    isDisabled: Boolean,
    isFullwidth: Boolean,
    isInverted: Boolean,
    isLight: Boolean,
    isLoading: Boolean,
    isOutlined: Boolean,
    isRounded: Boolean,
    isStatic: Boolean,
    size: String,
  },
  computed: {
    cls() {
      const cls = {
        "is-fullwidth": this.isFullwidth,
        "is-inverted": this.isInverted,
        "is-light": this.isLight,
        "is-loading": this.isLoading,
        "is-outlined": this.isOutlined,
        "is-rounded": this.isRounded,
        "is-static": this.isStatic,
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
