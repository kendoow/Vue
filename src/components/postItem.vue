<template>
  <div class="post">
    <div>
      <div><strong>Название:</strong> {{ post.title }}</div>
      <div><strong>Описание:</strong> {{ post.body }}</div>
    </div>
    <div class="post__btns">
      <ButtonBase @click="$emit('remove', post)">Delete</ButtonBase>
    </div>
  </div>
</template>
<script lang="ts">


export default {

  props: {
    post: {
      type: Array,
      required: true,
    }
  }
}
</script>
<style scoped>
.post {
  padding: 15px;
  border: 2px solid teal;
  margin-top: 15px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>