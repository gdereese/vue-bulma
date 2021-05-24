<template>
  <img :class="cls" />
</template>

<script>
export default {
  name: "Image",
  props: {
    isRounded: Boolean,
  },
  computed: {
    cls() {
      const cls = {
        "is-rounded": this.isRounded,
      };

      return cls;
    },
  },
};
</script>

<style></style>
