<template>
  <div>
    <post-form @create="createPost"/>
    <post-list :posts="posts"/>
  </div>

</template>

<script lang="ts">
import postForm from '@/components/postForm.vue';
import postList from '@/components/postList.vue';

export default {
  components: {
    postForm, postList
  },
  data() {
    return {
      posts: [
        {id: 1, title: 'Some title', body: "Some description"},
        {id: 2, title: 'Some title 2', body: "Some description 2"},
        {id: 3, title: 'Some title 3', body: "Some description 3"},
        {id: 4, title: 'Some title 4', body: "Some description 4"},
      ],
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
    }
  },

}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

</style>