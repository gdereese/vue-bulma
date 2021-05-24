<template>
  <nav class="level">
    <div class="level-left" v-if="$slots['left']">
      <slot name="left"></slot>
    </div>

    <slot v-if="$slots['default']"></slot>

    <div class="level-right" v-if="$slots['right']">
      <slot name="right"></slot>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Level",
  props: {
    isMobile: Boolean,
  },
  computed: {
    cls() {
      const cls = {
        "is-mobile": this.isMobile,
      };

      return cls;
    },
  },
};
</script>

<style></style>
