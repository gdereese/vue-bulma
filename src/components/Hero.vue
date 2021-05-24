<template>
  <section class="hero" :class="cls">
    <div class="hero-head" v-if="$slots['header']">
      <slot name="header"></slot>
    </div>
    <div class="hero-body" v-if="$slots['body']">
      <slot name="body"></slot>
    </div>
    <div class="hero-foot" v-if="$slots['footer']">
      <slot name="footer"></slot>
    </div>
  </section>
</template>

<script>
export default {
  name: "Hero",
  props: {
    color: String,
    size: String,
  },
  computed: {
    cls() {
      const cls = {};

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
