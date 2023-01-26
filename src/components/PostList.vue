<template>
    <div v-if="posts.length > 0">
        <h2>Список постов</h2>
        <post-item 
        :key="post.id" 
        v-for="post in posts" 
        :post="post"
        @remove="$emit('remove', post)"
        />
    </div>
    <h2 v-else style="color: burlywood;">Список постов пуст</h2>
</template>
/** @remove="$emit('remove', post)" 
Прокидываем пропсы из PostItem выше в App
* v-if удаляет полность компонент из DOM если false
что бы не удалять компонент используй v-show
*/
<script>
import PostItem from './PostItem.vue';
export default {   
components:{
        PostItem
},
  props: {
   posts: {
    type: Array,
    required: true
   },
  },
};
</script>

<style scoped>

form{
    display: flex;
    flex-direction: column;
}
.input{
    width: 100px;
    border: 1px solid teal;
    padding: 10px 15px;
    color: teal;
}
</style>
