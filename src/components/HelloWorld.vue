<template>
   <Table>
    <template #mergehead>
                <th rowspan="2" >S.no</th>
                <th colspan="2" >pokemon</th>
                <th colspan="3">Naruto</th>
    </template>
    <template #thead>
        <Head v-for="(i,index) in this.headvalue" :key="index" >{{i.label}}</Head>
        <Head >Slot 1</Head>
        <Head >Slot 2</Head>
    </template>
        <template #tbody>
          <tr v-for="(i,index) in this.rowvalue" :key="index" >
            <Cell>{{index+1}}</Cell>
            <Cell v-for="(j,col_index) in this.headvalue" :key="col_index">
                <div v-if="j.prop == 'tag'">
                   <span v-if="i[j.prop] === 'Success'"><button>Success</button></span>
                   <span v-else><button>Failed</button></span>
                </div>
                <div v-else>
                  {{i[j.prop]}}
                </div>
            </Cell>
            <Cell><input type="text" style="width: auto"></Cell>
            <Cell><button>Save</button></Cell>
          </tr>
    </template>
   </Table>
</template>

<script>
import Table from './table-v2/HlxTableV2.vue'
import Cell from './table-v2/HlxTableCell.vue'
import Head  from './table-v2/HlxTableHead.vue'

export default {
components:{
    Table,
    Cell,
    Head
},
data()
{
    return{
        headvalue:[{prop:'name',label:'Name'},{prop:'cartoon',label:'Cartoon'},{prop:'tag',label:'Tag'}],
        rowvalue:[{name:'Ash',cartoon:'pikachu',tag:'Success'},
        {name:'Brock',cartoon:'charizard',tag:'Failed'},
        {name:'Misty',cartoon:'ninja',tag:'Failed'},
        {name:'May',cartoon:'frookie',tag:'Success'},
        ]
    }
}
}
</script>

<style>

</style>