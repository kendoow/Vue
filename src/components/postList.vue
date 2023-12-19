<template>
  <div v-show="posts.length">
    <h3>List of users</h3>

    <post-item v-for="post in posts" :post="post" :key="post.id" @remove="$emit('remove', post)"/>
  </div>
  <h2 v-show="!posts.length">Empty</h2>
</template>
<script lang="ts">
import PostItem from "@/components/postItem.vue";

export default {
  components: {PostItem},
  props: {
    posts: {
      type: Array,
      required: true
    }
  }
}
</script>


<style scoped>

</style>