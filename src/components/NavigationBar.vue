<template>
  <nav class="navbar" role="navigation" aria-label="Navigation" :class="cls">
    <div class="navbar-brand">
      <slot name="brand"></slot>

      <a
        role="button"
        class="navbar-burger has-text-light"
        aria-label="menu"
        :aria-expanded="isBurgerActive"
        :class="{ 'is-active': isBurgerActive }"
        @click="burgerClick($event)"
        v-if="hasBurger"
      >
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </a>
    </div>

    <div class="navbar-menu">
      <div class="navbar-start">
        <slot name="menu-start"></slot>
      </div>

      <div class="navbar-end">
        <slot name="menu-end"></slot>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "NavigationBar",
  props: {
    color: String,
    fixed: String,
    hasBurger: Boolean,
    isSpaced: Boolean,
    isTransparent: Boolean,
  },
  data() {
    return {
      isBurgerActive: false,
    };
  },
  computed: {
    cls() {
      const cls = {
        "is-spaced": this.isSpaced,
        "is-transparent": this.isTransparent,
      };

      if (this.color) {
        const colorClassName = `is-${this.color.toLowerCase()}`;
        cls[colorClassName] = true;
      }
      if (this.fixed) {
        const fixedClassName = `is-fixed-${this.fixed.toLowerCase()}`;
        cls[fixedClassName] = true;
      }

      return cls;
    },
  },
  methods: {
    burgerClick(event) {
      this.isBurgerActive = !this.isBurgerActive;
      this.$emit("burger-click", event.target);
    },
  },
};
</script>

<style></style>
