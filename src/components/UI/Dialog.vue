<script lang="ts">
export default {
  name: 'DialogBase',
  props: {
    show: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    hideDialog() {
      this.$emit('update:show', false)
    }
  }
}
</script>

<template>
  <div class="dialog" v-if="show" @click.stop="hideDialog">
    <div @click.stop class="dialogContent">
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>
.dialog {
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  display: flex;
}

.dialogContent {
  margin: auto;
  background: white;
  border-radius: 12px;
  padding: 20px;
}
</style>