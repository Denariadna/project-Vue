<template>
    <div class="app">
        <post-form  @create="createPost"/>
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
                { id: 1, title: 'Пост о котах', body: 'Мягкие пушистые красивые' },
                { id: 2, title: 'Пост о котах 2', body: 'Мягкие пушистые красивые' },
                { id: 3, title: 'Пост о котах 3', body: 'Мягкие пушистые красивые' },
                { id: 4, title: 'Пост о котах 4', body: 'Мягкие пушистые красивые' }
            ]
        }
    },

    methods: {
        createPost(post) {
            this.posts.push(post)
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