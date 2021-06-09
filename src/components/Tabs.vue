<template>
  <div class="tabs" :class="cls">
    <ul>
      <slot></slot>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Tabs",
  props: {
    alignment: String,
    size: String,
    isBoxed: Boolean,
    isFullwidth: Boolean,
    isToggle: Boolean,
    isToggleRounded: Boolean,
  },
  computed: {
    cls() {
      const cls = {
        "is-boxed": this.isBoxed,
        "is-fullwidth": this.isFullwidth,
        "is-toggle": this.isToggle,
        "is-toggle-rounded": this.isToggleRounded,
      };

      if (this.alignment) {
        const alignmentClassName = `is-${this.alignment.toLowerCase()}`;
        cls[alignmentClassName] = true;
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
