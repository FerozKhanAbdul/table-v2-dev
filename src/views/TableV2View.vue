<template>
  <hlx-table-v2
    :theads="6"
    :border="['table', 'header', 'vertical', 'horizontal']"
    :boldHeaders="false"
    :rowHover="false"
    theme="primary"
    :stripedRows="false"
  >
    <template #mergehead>
                <hlx-table-head rowspan="2" style="width: 20px !important">S.no</hlx-table-head>
                <hlx-table-head colspan="2">pokemon</hlx-table-head>
                <hlx-table-head colspan="3" >Naruto</hlx-table-head>
    </template>
    <template #thead>
      <hlx-table-head v-for="(i, index) in this.headvalue" :key="index" >{{
        i.label
      }}</hlx-table-head>
      <hlx-table-head :align="'right'">Slot 1</hlx-table-head>
      <hlx-table-head>Slot 2</hlx-table-head>
    </template>
    <template #tbody>
      <tr v-for="(i, index) in this.rowvalue" :key="index">
        <hlx-table-cell>{{index+1}}</hlx-table-cell>
        <hlx-table-cell
          v-for="(j, col_index) in this.headvalue"
          :key="col_index"
        >
          <div v-if="j.prop == 'tag'">
            <span v-if="i[j.prop] === 'Success'"><button>Success</button></span>
            <span v-else><button>Failed</button></span>
          </div>
          <div v-else>
            {{ i[j.prop] }}
          </div>
        </hlx-table-cell>
        <hlx-table-cell><input type="text" /></hlx-table-cell>
        <hlx-table-cell :align="'right'"><button>Save</button></hlx-table-cell>
      </tr>
    </template>
  </hlx-table-v2>

  <br />
  <br />
  <br />

  <hlx-table-v2 :theads="6">
    <template #mergehead>
      <hlx-table-head rowspan="2" style="width: 20px !important"
        >S.no</hlx-table-head
      >
      <hlx-table-head colspan="2">pokemon</hlx-table-head>
      <hlx-table-head colspan="3">Naruto</hlx-table-head>
    </template>
    <template #thead>
      <hlx-table-head v-for="(i, index) in this.headvalue" :key="index">{{
        i.label
      }}</hlx-table-head>
      <hlx-table-head>Slot 1</hlx-table-head>
      <hlx-table-head style="width: 30px">Slot 2</hlx-table-head>
    </template>
    <template #tbody>
      <tr v-for="(i, index) in this.rowvalue" :key="index">
        <hlx-table-cell>{{ index + 1 }}</hlx-table-cell>
        <hlx-table-cell
          v-for="(j, col_index) in this.headvalue"
          :key="col_index"
        >
          <div v-if="j.prop == 'tag'">
            <span v-if="i[j.prop] === 'Success'"><button>Success</button></span>
            <span v-else><button>Failed</button></span>
          </div>
          <div v-else>
            {{ i[j.prop] }}
          </div>
        </hlx-table-cell>
        <hlx-table-cell><input type="text" /></hlx-table-cell>
        <hlx-table-cell><button>Save</button></hlx-table-cell>
      </tr>
    </template>
  </hlx-table-v2>
</template>

<script>
import HlxTableV2 from "../components/table-v2/HlxTableV2.vue";
import HlxTableCell from "../components/table-v2/HlxTableCell.vue";
import HlxTableHead from "../components/table-v2/HlxTableHead.vue";

export default {
  components: {
    HlxTableV2,
    HlxTableCell,
    HlxTableHead,
  },
  data() {
    return {
      headvalue: [
        { prop: "name", label: "Name" },
        { prop: "cartoon", label: "Cartoon" },
        { prop: "tag", label: "Tag" },
      ],
      rowvalue: [
        { name: "Ash", cartoon: "pikachu", tag: "Success" },
        { name: "Brock", cartoon: "charizard", tag: "Failed" },
        { name: "Misty", cartoon: "ninja", tag: "Failed" },
        { name: "May", cartoon: "frookie", tag: "Success" },
      ],
    };
  },
};
</script>

<style></style>
