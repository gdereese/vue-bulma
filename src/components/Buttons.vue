<template>
  <div class="buttons" :class="cls">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "Buttons",
  props: {
    alignment: String,
    hasAddons: Boolean,
  },
  computed: {
    cls() {
      const cls = {
        "has-addons": this.hasAddons,
      };

      if (this.alignment) {
        const alignmentClassName = `is-${this.alignment}`;
        cls[alignmentClassName] = true;
      }

      return cls;
    },
  },
};
</script>

<style></style>
