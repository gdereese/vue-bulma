<template>
  <div class="modal">
    <div class="modal-background"></div>
    <div class="modal-card">
      <header class="modal-card-head">
        <p class="modal-card-title" v-if="$slots['header-title']">
          <slot name="header-title"></slot>
        </p>
        <button class="delete" aria-label="close"></button>
      </header>
      <section class="modal-card-body">
        <slot name="body"></slot>
      </section>
      <footer class="modal-card-foot" v-if="$slots['footer']">
        <slot name="footer"></slot>
      </footer>
    </div>
  </div>
</template>

<script>
export default {
  name: "ModalCard",
};
</script>

<style></style>
