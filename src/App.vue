<template>
  <div class="app">
    <h1>Страница с постами</h1>
    <my-button @click="showDialog">Создать пост</my-button>
    <my-dialog v-model:show="dialogVisible">
      <post-form @create="createPost" />
    </my-dialog>

    <post-list v-bind:posts="posts" @remove="removePost" />

  </div>
</template>

<script>
import PostList from './components/PostList.vue'
import PostForm from './components/PostForm.vue'
export default {
  components: {
    PostList, PostForm
  },
  data() {
    return {
      posts: [
        { id: 1, title: 'Js1', body: 'Описание поста' },
        { id: 2, title: 'Js1', body: 'Описание поста1' },
        { id: 3, title: 'Js1', body: 'Описание поста2' },
        { id: 4, title: 'Js1', body: 'Описание поста3' },
      ],
      dialogVisible: false

    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
      this.dialogVisible = false
    },
    removePost(post) {
      this.posts = this.posts.filter(p => p.id != post.id)
    },
    showDialog() {
      this.dialogVisible = true;
    }
  }
}
</script>

<style>
#app {}
</style>
