<template>
    <form @submit.prevent>
        <h2>Создать пост</h2>
        <my-input v-model="post.title" type="text" placeholder="Название поста" />
        <my-input v-model="post.body" class="input" type="text" placeholder="Описание поста" />
        <my-button class="btn" @click="createPost" style="align-self: flex-end; margin-top: 15px">
            Создать пост
        </my-button>
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
</style>