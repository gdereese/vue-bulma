<template>
  <table class="table" :class="cls">
    <thead v-if="showHeader">
      <slot name="header">
        <tr>
          <th v-for="(col, idx) in columns || []" :key="idx">
            {{ col.label }}
          </th>
        </tr>
      </slot>
    </thead>
    <tbody>
      <tr
        :class="getRowClass(item)"
        :key="itemIdx"
        @click="onRowClick(item, $event)"
        v-for="(item, itemIdx) in items || []"
      >
        <td
          v-for="(col, colIdx) in columns || []"
          v-html="getCellHtml(item, col)"
          :key="colIdx"
        ></td>
      </tr>
    </tbody>
    <tfoot v-if="showFooter">
      <slot name="footer"></slot>
    </tfoot>
  </table>
</template>

<script>
export default {
  name: "Table",
  props: {
    columns: Array,
    isBordered: Boolean,
    isFullwidth: Boolean,
    isHoverable: Boolean,
    isNarrow: Boolean,
    isStriped: Boolean,
    items: Array,
    rowClass: [Object, String],
    selectedItem: Object,
    showHeader: {
      type: Boolean,
      default: true,
    },
    showFooter: Boolean,
  },
  computed: {
    cls() {
      const cls = {
        "is-bordered": this.isBordered,
        "is-fullwidth": this.isFullwidth,
        "is-hoverable": this.isHoverable,
        "is-narrow": this.isNarrow,
        "is-striped": this.isStriped,
      };

      return cls;
    },
  },
  methods: {
    getCellHtml(item, col) {
      if (col.template) {
        return col.template(item);
      } else if (col.name) {
        return item[col.name];
      }
      return null;
    },
    getRowClass(item) {
      var cls = null;
      if (
        typeof this.rowClass === "string" ||
        this.rowClass instanceof String
      ) {
        for (const name of this.rowClass.split(" ")) {
          cls = {};
          cls[name] = true;
        }
      } else {
        cls = {
          ...this.rowClass,
        };
      }

      cls["is-selected"] = item == this.selectedItem;

      return cls;
    },
    onRowClick(item, event) {
      this.$emit("row-click", { item, event });
    },
  },
};
</script>

<style></style>
