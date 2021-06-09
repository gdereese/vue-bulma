<template>
  <li :class="cls">
    <a>
      <slot></slot>
    </a>
  </li>
</template>

<script>
export default {
  name: "Tab",
  props: {
    isActive: Boolean
  },
  computed: {
    cls() {
      const cls = {
        "is-active": this.isActive,
      };

      return cls;
    },
  },
}
</script>

<style></style>
