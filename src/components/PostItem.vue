<template>
    <div class="post">
        <div>
            
            <div><strong>Название</strong>{{ post.title }}</div>
            <div><strong>Описание</strong>{{ post.body }}</div>
        </div>
        <my-button 
        @click="$emit('remove', post)" 
        class="post_buttons"
        >Delete</my-button>
    </div>
</template>
/** @click="$emit('remove', post)"
* Прокидываем пропсы выше в PostList
*/
<script>

export default {
    
    props: {
        post: {
            type: Object,
            required: true
        },
    },

};
</script>

<style scoped>
.post {
    display: flex;
    padding: 15px;
    border: 2px solid teal;
    margin-top: 15px;
    align-items: center;
    justify-content: space-between;
}



.input {
    width: 100px;
    border: 1px solid teal;
    padding: 10px 15px;
    color: teal;
}
</style>
