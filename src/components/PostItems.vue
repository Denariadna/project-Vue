<template>
    <div class="post">
        <div>
            <h2>{{ post.title }}</h2>
            <p>{{ post.body }}</p>
        </div>
        <div class="post_btns">
            <my-button>Удалить</my-button>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        post: {
            type: Object,
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
    display: flex;
    align-items: center;
    justify-content: space-between;
}
</style>