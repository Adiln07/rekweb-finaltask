<style scoped>
.container{
    background-color: #14213d;
    color: white;
    /* height:100vh ; */
    font-family: Arial, Helvetica, sans-serif;
}

nav{
    background-color: #fca311;
    width: 100%;
    height: 5em;
    text-align: center;
}

.link-nav{
    line-height: 3em;
    color: white;
    font-size: 1.6em;
    font-weight: 700;
    text-decoration: none;
    transition: .5s;
}
.link-nav:hover{
    color: #e5e5e5;
    transition: .5s;
}

.post__block{
    margin: auto;
    width: 25em;
    /* height: em; */
    background-color: white;
    color: black;
    text-align: center;
    border-radius: 15px;
    margin-top: 2em;
    
}

.content{
    padding-top: .2em;
}
.link-content{
    background-color: black;
    height: 3em;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 1em;
    border-bottom-left-radius: 15px;
    border-bottom-right-radius: 15px;
}

.link-content .link{
    color: white;
    text-decoration: none;
}

</style>

<template>
    <div class="container" >
        <nav>
            <Link href="/post/create" class="link-nav">Create Post </Link>
        </nav>

        <div class="post__block" v-for="post in posts" :key="post.id">
            <div class="content">
                <h2> {{ post.title }}</h2>
                <p>{{ post.author }}</p>
            </div>
            
            <div class="link-content">
                <Link class="link" :href="`/post/${post.id}`">Selengkapnya</Link>
                <Link class="link" :href="`/post/edit/${post.id}`">Edit</Link>
                <Link class="link" :href="`/post/delete/${post.id}`" method="DELETE">Hapus</Link>
            </div>
            
        </div>

    </div>
</template>

<script setup>
import { defineProps } from "vue";
import { Link } from "@inertiajs/vue3"

defineProps({
    posts: Object
});
</script>