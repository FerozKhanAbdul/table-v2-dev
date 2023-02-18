<template>
<td>
    <slot></slot>
</td>
</template>
<script>

export default {
   
   props:{
    cellvalue:{
        type:String
    }
   }
}
</script>
