<template>
    <div class="post" v-for="post in posts" :key="post.id">
            <h2>{{ post.title }}</h2>
            <p>{{ post.body }}</p>
        </div>
</template>

<script>
export default {
 props: {
     posts: {
         type: Array,
         required: true
     }
 }
}
</script>

<style>
.post {
    padding: 15px;
    border: 2px solid teal;
    margin-top: 15px;
}

</style>