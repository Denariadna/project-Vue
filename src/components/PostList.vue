<template>
    <div>
        <h2>Список котиков</h2>
        <post-item v-for="post in posts" :key="post.id" :post="post">
        </post-item>
    </div>
</template>

<script>
import PostItem from './PostItems.vue';
export default {
    components: { PostItem },
    props: {
        posts: {
            type: Array,
            required: true
        }
    }
}
</script>

<style></style>