<style scoped>
.post__content{
    background-color: #14213d;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: Arial, Helvetica, sans-serif;
    
}

.content-card{
    background-color: white;
    width: 35em;
    text-align: center;
    border-radius: 15px;
}

.content-card p{
    font-size: 1.5em;
    font-weight: 500;
}

.content-bottom{
    background-color: black;
    color: white;
    border-bottom-left-radius: 15px;
    border-bottom-right-radius: 15px;
    height: 5em;
    display: flex;
    align-items: center;
}
</style>

<template>
    
    <div class="post__content">
        <div class="content-card">
            <h1>{{ post.title }}</h1>
            <p>{{ post.author }}</p>
            <div class="content-bottom">
                {{ post.content }}
            </div>
        </div>
        
    </div>
    
</template>

<script setup>
import { defineProps } from 'vue';


defineProps({
    post: Object
})
</script>