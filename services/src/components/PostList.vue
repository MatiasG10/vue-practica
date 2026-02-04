<template>
    <div>Listado de posts</div>
    <ul class="post-list">
        <li v-for="post in posts" :key="post.id">{{ post.title }}</li>
    </ul>
</template>

<script lang="ts" setup>

import PostService from '@/services/PostService';
import { defineComponent, onMounted } from 'vue';

const service = new PostService()
const posts = service.getPosts()

onMounted(async () => {
    await service.fetchAll()
})


// import PostService from '@/services/PostService';
// import { defineComponent, onMounted } from 'vue';

// export default defineComponent({
//     name: 'PostList',
//     setup() {
//        const service = new PostService()
//        const posts = service.getPosts() 


//        onMounted(async () =>{
//             await service.fetchAll()
//        })

//        return {
//         posts
//        }
//     }

// });

//option API
// import PostService from '@/services/PostService';
// import { defineComponent, onMounted } from 'vue';

// export default defineComponent({
//     name: 'PostList',
//     data() {
//         const service = new PostService()
//         const posts = service.getPosts()
//         return {posts, service}
//     },
//     async mounted() {
//         await this.service.fetchAll()
//     }

// });


</script >

<style scope>
    .post-list {
        width: 95vw;
        height: 75px;
        padding: 20px;
        list-style-type: none;
    }

    .post-list li {
        width: 100%;
        padding: 10px;
        border: 1px solid #ccc;
    }
</style>