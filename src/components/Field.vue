<template>
  <div class="field" :class="cls">
    <label class="label" :class="labelCls" v-if="label">{{ label }}</label>
    <slot></slot>
    <p class="help" v-if="help">{{ help }}</p>
  </div>
</template>

<script>
export default {
  name: "Field",
  props: {
    addonAlign: String,
    groupAlign: String,
    groupMultiline: Boolean,
    hasAddons: Boolean,
    help: String,
    isGrouped: Boolean,
    label: String,
    size: String,
  },
  computed: {
    cls() {
      const cls = {
        "has-addons": this.hasAddons,
        "is-grouped": this.isGrouped,
        "is-grouped-multiline": this.groupMultiline,
      };

      if (this.groupAlign) {
        const groupAlignClassName = `is-grouped-${this.groupAlign.toLowerCase()}`;
        cls[groupAlignClassName] = true;
      }

      return cls;
    },
    labelCls() {
      const cls = {};

      if (this.addonAlign) {
        const addonAlignClassName = `has-addons-${this.addonAlign.toLowerCase()}`;
        cls[addonAlignClassName] = true;
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
