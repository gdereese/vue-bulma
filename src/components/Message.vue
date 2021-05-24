<template>
  <article class="message" :class="cls">
    <div class="message-header" v-if="$slots['header-title']">
      <p v-if="$slots['header-title']">
        <slot name="header-title"></slot>
      </p>
      <button
        class="delete"
        aria-label="delete"
        :class="buttonCls"
        v-if="showDelete"
      ></button>
    </div>
    <div class="message-body">
      <slot name="body"></slot>
    </div>
  </article>
</template>

<script>
export default {
  name: "Message",
  props: {
    showDelete: Boolean,
    size: String,
  },
  computed: {
    buttonCls() {
      const cls = {};

      if (this.size) {
        const sizeClassName = `is-${this.size.toLowerCase()}`;
        cls[sizeClassName] = true;
      }

      return cls;
    },
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
