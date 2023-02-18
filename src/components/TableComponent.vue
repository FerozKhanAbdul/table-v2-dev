<template>
    <!-- <table>
        <thead>
            <tr>
                <th v-for="column in column" :key="column.field">{{ column.label }}</th>
                <slot name="header"></slot>
            </tr>
        </thead>
        <tbody>
         <tr>
                 <slot></slot>
            </tr>
            
        </tbody>
    </table> -->
        <slot/>
</template>

<script>
import { ref, provide } from 'vue'

export default ({
    props:{
        data:{
            type:Array,
        },
        column: {
      type: Array,
      required: true
    }
    },
    component:{
        // hlxColumn
    },
    mounted()
    {
        // console.log(this.column);
        // provide(/* key */ 'message', /* value */ this.data)
    },
       setup (props, { slots }) {
      const tableColumns1 = ref(slots.default().map((table) => table.props))
      const tableColumns = ref(tableColumns1.value)
      console.log(tableColumns,'opiuhygf');
      provide('columnNames', tableColumns)
      return {
        tableColumns,
        tableColumns1
      }
    }
    

})
</script>
