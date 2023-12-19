<template>
  <div>
    <h1>Страница с постами</h1>
    <ButtonBase @click="showDialog">Create Post</ButtonBase>
    <DialogBase v-model:show="dialogShow">
      <post-form @create="createPost"/>

    </DialogBase>
    <post-list :posts="posts" @remove="removePost"/>
  </div>

</template>

<script lang="ts">
import postForm from '@/components/postForm.vue';
import postList from '@/components/postList.vue';
import ButtonBase from "@/components/UI/Button.vue";

export default {
  components: {
    ButtonBase,
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
      dialogShow: false
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
      this.dialogShow = false
    },
    removePost(post) {
      this.posts = this.posts.filter((postItem) => postItem.id !== post.id)
    },
    showDialog() {
      this.dialogShow = true
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