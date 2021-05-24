<template>
  <span :class="cls">{{ name }}</span>
</template>

<script>
export default {
  name: "MaterialIcon",
  props: {
    iconStyle: String,
    name: String,
  },
  computed: {
    cls() {
      const cls = {};

      if (this.iconStyle) {
        const iconStyleClassName = `material-icons-${this.iconStyle.toLowerCase()}`;
        cls[iconStyleClassName] = true;
      } else {
        cls["material-icons"] = true;
      }

      return cls;
    },
  },
};
</script>

<style></style>
