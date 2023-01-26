<template>
  <form @submit.prevent>

    <h4>Создание поста</h4>
    <my-input v-model="post.title" type="text"  placeholder="название" />
    <my-input v-model="post.body" type="text"  placeholder="название" />
    <div class="btn">
      <my-button  style='' @click="createPost">Создать</my-button>
    </div>
  </form>
</template>

<script>

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
      this.$emit('create', this.post),
        this.post = {
          title: '',
          body: ''
        }
    }

  }
};
</script>

<style scoped>
.post {
  padding: 15px;
  border: 2px solid teal;
  margin-top: 15px;
}

form {
  display: flex;
  flex-direction: column;
}
.btn{
  margin-top: 10px;
  align-self:flex-end;
}
</style>

