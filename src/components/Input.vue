<template>
  <input
    class="input"
    :class="cls"
    :disabled="isDisabled"
    :readonly="isReadonly"
    :value="modelValue"
    @input="$emit('update:modelValue', $event.target.value)"
  />
</template>

<script>
export default {
  name: "Input",
  props: {
    color: String,
    isDisabled: {
      type: Boolean,
      default: false,
    },
    isFocused: Boolean,
    isHovered: Boolean,
    isReadonly: {
      type: Boolean,
      default: false,
    },
    isRounded: Boolean,
    isStatic: {
      type: Boolean,
      default: false,
    },
    modelValue: String,
    size: String,
  },
  computed: {
    cls() {
      const cls = {
        "is-focused": this.isFocused,
        "is-hovered": this.isHovered,
        "is-rounded": this.isRounded,
        "is-static": this.isStatic,
      };

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
