<script lang="ts">
export default {
  name: 'ButtonBase'
}
</script>

<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<style scoped>
.btn {
  padding: 10px 15px;
  color: teal;
  border: 1px solid teal;
  cursor: pointer;
}
</style>