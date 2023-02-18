<template>
<td :style="{textAlign: this.align }">
    <slot></slot>
</td>
</template>
<script>

export default {
   
   props:{
    align:{
        type:String,
        default: 'center'
    }
   }
}
</script>
