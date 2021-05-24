<template>
  <div class="card">
    <header
      class="card-header"
      v-if="$slots['header-title'] || $slots['header-icon']"
    >
      <p class="card-header-title" v-if="$slots['header-title']">
        <slot name="header-title"></slot>
      </p>
      <slot name="header-icon"></slot>
    </header>
    <div class="card-image" v-if="$slots['image']">
      <slot name="image"></slot>
    </div>
    <div class="card-content" v-if="$slots['content']">
      <slot name="content"></slot>
    </div>
    <footer class="card-footer" v-if="$slots['footer']">
      <slot name="footer"></slot>
    </footer>
  </div>
</template>

<script>
export default {
  name: "Card",
};
</script>

<style></style>
