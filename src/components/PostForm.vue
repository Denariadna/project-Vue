<template>
<form @submit.prevent>
            <h2>Создать пост</h2>
            <input v-model="post.title" class="input" type="text"
                placeholder="Название поста">
            <input v-model="post.body"  class="input" type="text"
                placeholder="Описание поста">
            <button class="btn" @click="createPost">Создать пост</button>
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
            this.post.id = Date.now()
            this.$emit('create', this.post)
            this.post = {
                title: '',
                body: '',
            }
        }
    }
}
</script>

<style>
form {
    display: flex;
    flex-direction: column;
}

.btn {
    margin-top: 15px;
    align-self: flex-end;
    padding: 10px 15px;
    background: none;
    color: turquoise;
    border: 1px solid turquoise;
}

.input {
    width: 100%;
    padding: 10px;
    border: 1px solid teal;
    margin-top: 15px;
}
</style>