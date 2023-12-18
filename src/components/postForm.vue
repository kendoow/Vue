<template>
  <h4>Создание поста</h4>
  <form @submit.prevent>
    <InputBase v-model="post.title" type="text"
               placeholder="Название поста"/>
    <InputBase v-model="post.body" type="text"
               placeholder="Описание поста"/>
    <ButtonBase class="btn" @click="createPost">Создать</ButtonBase>
  </form>
</template>
<script lang="ts">


export default {

  data() {
    return {
      post: {
        title: '',
        body: ''
      }
    }
  },
  methods: {
    createPost() {

      this.post.id = Date.now();

      this.$emit('create', this.post)
      this.post = {
        title: '',
        body: ''
      }

    }
  },
}
</script>


<style scoped>
form {
  display: flex;
  flex-direction: column;
}

</style>