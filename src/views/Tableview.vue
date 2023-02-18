<template>
<!-- <hlx-table>
<hlx-column v-for="(i,index) in this.columns" :key="index" :prop="i.field" :label="i.label">
   
</hlx-column>
</hlx-table> -->
<!-- <hlx-table :data="this.tableData" :column="this.columns">
<hlx-column v-for="(i,index) in this.columns" :key="index" :label="i.label" :prop="i.field" :data="tableData">
  <template v-slot:default="slotProps">
    {{slotProps.hello}}
  </template>

</hlx-column>
<hlx-column>
  <template v-slot:table>
    <p>ksfgzk</p>
  </template>
</hlx-column>
    <template v-slot:header>
      <th>Actions</th>
    </template>
    <template v-slot:row>
        <button>Edit</button>
        <button>Delete</button>
    </template>
</hlx-table> -->











</template>

<script>
import hlxTable from '../components/TableComponent.vue';
import hlxColumn from '../components/TableColumnComponent.vue';

export default {
  components: {
    hlxTable,
    hlxColumn
  },
  data() {
    return {
      columns: [
        { label: 'Name', field: 'name' },
        { label: 'Age', field: 'age' },
        { label: 'Address', field: 'address' }
      ],
      tableData: [
        { name: 'John Doe', age: 30, address: 'USA' },
        { name: 'Jane Doe', age: 28, address: 'UK' },
        { name: 'Jim Smith', age: 32, address: 'Canada' }
      ]
    };
  }
};
</script>
