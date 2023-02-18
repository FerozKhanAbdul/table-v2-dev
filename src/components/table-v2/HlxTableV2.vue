<template>
  <table
    :class="{
      hlxTableV2: true,
      headerBorder: this.border.includes('header') ? true : false,
      tableBorder: this.border.includes('table') ? true : false,
      horizontalBorder: this.border.includes('horizontal') ? true : false,
      verticalBorder: this.border.includes('vertical') ? true : false,
      lightTheme: this.theme === 'light' ? true : false,
      primaryTheme: this.theme === 'primary' ? true : false,
      boldHeaders: this.boldHeaders,
      rowHover: this.rowHover,
      stripedRow: this.stripedRows,
    }"
    :id="'table-v2-' + this.unique"
  >
    <colgroup style="width: 100% !important">
      <col v-for="heads in this.theads" :key="heads" />
    </colgroup>
    <thead>
      <tr>
        <slot name="mergehead"></slot>
      </tr>
      <tr>
        <slot name="thead"></slot>
      </tr>
    </thead>
    <tbody>
      <slot name="tbody"></slot>
    </tbody>
  </table>
</template>

<script>
export default {
  props: {
    theads: {
      type: Array,
    },
    border: {
      type: Array,
      default: [],
    },
    boldHeaders: {
      type: Boolean,
      default: false,
    },
    rowHover: {
      type: Boolean,
      default: false,
    },
    theme: {
        type: String,
        default: 'light'
    },
    stripedRows: {
        type: Boolean,
        default: false
    }
  },
  data() {
    return {
      unique: Math.floor(Math.random() * 1000 + 1),
    };
  },
};
</script>
<style lang="scss">
// ----------------------------------------- Basic table css -----------------------------------------
.hlxTableV2 {
  border-collapse: separate !important;
  border-spacing: 0;
  width: 100%;
  font-family: "OpenSans";
  background: white;
  th,
  td {
    padding: 10px;
    font-weight: 100;
  }
}

// ----------------------------------------- Bold headers css -----------------------------------------
.boldHeaders {
  th {
    font-weight: bold;
  }
}

// ----------------------------------------- Borders css -----------------------------------------

.tableBorder {
  border: solid #ccc 1px;
  -moz-border-radius: 6px;
  -webkit-border-radius: 6px;
  border-radius: 6px;
}

.headerBorder {
  th {
    border-bottom: 1px solid #d8d8d8;
  }
}

.verticalBorder {
  th,
  td {
    border-right: 1px solid #d8d8d8;
  }
  th:last-child,
  td:last-child {
    border-right: none;
  }
}

.horizontalBorder {
  td {
    border-bottom: 1px solid #d8d8d8;
  }
  tr:last-child td {
    border-bottom: none;
  }
}

// ----------------------------------------- Borders css -----------------------------------------
.rowHover {
    tr:hover {
        background: #e4fff5;
    }
}

// ----------------------------------------- Theme css -----------------------------------------
.lightTheme {
    th {
        background: white;
    }
}
.primaryTheme {
    th {
        background: #54bd95;
        color: white;
    }
}

// ----------------------------------------- striped row css -----------------------------------------

.stripedRow {
    tr:nth-child(even) {
        background: #e4fff5;
    }
}
</style>
