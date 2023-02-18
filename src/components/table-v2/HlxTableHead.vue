<template>
  <th :style="{width: this.width+'px', textAlign: this.align }"><slot></slot></th>
</template>

<script>
export default {
  props: {
    width: {
      type: Number
    },
    align: {
      type: String,
      default: 'center'
    }
  }
}
</script>

<style>

</style>