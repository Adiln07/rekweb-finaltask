<style scoped>
.post__Edit{
    background-color: #14213d;
    height: 100vh;
    font-family: Arial, Helvetica, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
}

form{
    background-color: white;
    width: 30em;
    height: 20em;
    border-radius: 15px;
}

.title{
    padding-top: 1em;
    text-align: center;
}
.title label{
    display: block;
    font-size: 1.4em;
    font-weight: 700;
}

.title input{
    width: 25em;
    height: 2em;
    border-radius: 10px;
    background-color: #e5e5e5;
}

.author{
    padding-top: 1em;
    text-align: center;
}
.author label{
    display: block;
    font-size: 1.4em;
    font-weight: 700;
}

.author input{
    width: 25em;
    height: 2em;
    border-radius: 10px;
    background-color: #e5e5e5;
}

.content{
    padding-top: 1em;
    text-align: center;
}
.content label{
    display: block;
    font-size: 1.4em;
    font-weight: 700;
}

.content textarea{
    width: 25em;
    height: 5em;
    border: 2px solid black;
    border-radius: 10px;
    background-color: #e5e5e5;
}

.submit {
    padding-top: .5em;
    text-align: center;
}   
</style>

<template>
    <div class="post__Edit">

        <form @submit.prevent="form.put(`/post/update/${post.id}`)">
            <div class="title">
                <label>Judul Lagu</label>
                <input type="text" v-model="form.title"/>
            </div>
            <div class="author">
                <label>Nama Band</label>
                <input type="text" v-model="form.author"/>
            </div>
            <div class="content">
                <label>Makna Lagu</label>
                <textarea v-model="form.content"></textarea>
            </div>
            <div class="submit">
                <input type="submit" value="Update Post" />
            </div>
        </form>

    </div>
</template>

<script setup>
    import { useForm } from '@inertiajs/vue3';
    import { defineProps } from 'vue';

    let props = defineProps({
        post: Object
    });

    const form = useForm({
        title: props.post.title,
        author: props.post.author,
        content: props.post.content
    });
</script>