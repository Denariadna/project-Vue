<template>
    <div class="app">
        <post-form/>
        <PostList :posts="posts"/>
    </div>
</template>

<script>
import PostForm from './components/PostForm.vue';
import PostList from './components/PostList.vue';

export default {
    components: {
        PostList, PostForm
    },
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
</style>