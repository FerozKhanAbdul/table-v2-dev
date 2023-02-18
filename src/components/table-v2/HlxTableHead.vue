<template>
  <th :style="{width: this.width+'px'}"><slot></slot></th>
</template>

<script>
export default {
  props: {
    width: {
      type: Number
    }
  }
}
</script>

<style>

</style>