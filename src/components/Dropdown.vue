<template>
  <div class="dropdown" :class="cls">
    <div class="dropdown-trigger">
      <button class="button" aria-haspopup="true" aria-controls="dropdown-menu">
        <span>{{ text }}</span>
        <slot name="trigger-icon"></slot>
      </button>
    </div>
    <div class="dropdown-menu" id="dropdown-menu" role="menu">
      <div class="dropdown-content">
        <slot name="content"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Dropdown",
  props: {
    isActive: Boolean,
    isHoverable: Boolean,
    isRight: Boolean,
    isUp: Boolean,
    text: String,
  },
  computed: {
    cls() {
      const cls = {
        "is-active": this.isActive,
        "is-hoverable": this.isHoverable,
        "is-right": this.isRight,
        "is-up": this.isUp,
      };

      return cls;
    },
  },
};
</script>

<style></style>
