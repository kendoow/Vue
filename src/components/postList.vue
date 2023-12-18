<template>
  <div>
    <h3>List of users</h3>
  </div>
  <post-item v-for="post in posts" :post="post"/>
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