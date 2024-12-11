<template>
<form @submit.prevent>
            <h2>Создать пост</h2>
            <input v-bind:value="title" @input="title = $event.target.value" class="input" type="text"
                placeholder="Название поста">
            <input v-bind:value="body" @input="body = $event.target.value" class="input" type="text"
                placeholder="Описание поста">
            <button class="btn" @click="createPost">Создать пост</button>
        </form>
</template>

<script></script>

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