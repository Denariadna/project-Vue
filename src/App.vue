<template>
    <div class="app">
        <form @submit.prevent>
            <h2>Создать пост</h2>
            <input v-bind:value="title" @input="title = $event.target.value" class="input" type="text"
                placeholder="Название поста">
            <input v-bind:value="body" @input="body = $event.target.value" class="input" type="text"
                placeholder="Описание поста">
            <button class="btn" @click="createPost">Создать пост</button>
        </form>
        <div class="post" v-for="post in posts" :key="post.id">
            <h2>{{ post.title }}</h2>
            <p>{{ post.description }}</p>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            posts: [
                { id: 1, title: 'Пост о котах', description: 'Мягкие пушистые красивые' },
                { id: 2, title: 'Пост о котах 2', description: 'Мягкие пушистые красивые' },
                { id: 3, title: 'Пост о котах 3', description: 'Мягкие пушистые красивые' },
                { id: 4, title: 'Пост о котах 4', description: 'Мягкие пушистые красивые' }
            ],
            title: '',
            body: '',
        }
    },

    methods: {
        createPost() {
            const newPost = {
                id: Date.now(),
                title: this.title,
                description: this.body
            }
            this.posts.push(newPost)
            this.title = ''
            this.body = ''
        }
    }
}
</script>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.app {
    padding: 20px;
}

.post {
    padding: 15px;
    border: 2px solid teal;
    margin-top: 15px;
}

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