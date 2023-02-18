<template>
      <th>{{ label }}</th>
      <tr v-for="(row,index) in this.data" :key="index">
      <td><slot :row="row">{{ row[prop] }}</slot> </td>
      </tr>
</template> 

<script>
import { inject } from 'vue'

export default {
  // setup() {
  //   this.hello = inject('message')
  //   return { message }
  // },
  props:{
    prop:{
      type:String
    },
    label:{
       type:String
    }
    // data:{
    //   type:Array
    // }
  },
  data()
  {
    return{
       hello:[],
             data: [
        { name: 'John Doe', age: 30, address: 'USA' },
        { name: 'Jane Doe', age: 28, address: 'UK' },
        { name: 'Jim Smith', age: 32, address: 'Canada' }
      ]
    }
  },
  mounted()
  {
    //  this.hello = inject('message')
    // console.log(x);
  },
    setup () {
    const x = inject('columnNames')
      console.log(x);
      
    return {
      x
    }
  },
};
</script>
