<template>
    <div class="post">
        <h3>{{ title }}</h3>
        <p>{{ content }}</p>
        <input type="text" v-model="message">

        <button @click="handleClick()">Di hola</button>
    </div>
</template>

<script lang="ts">
import { defineComponent, Ref, ref } from 'vue';
export default defineComponent({
    name: 'PostDetail',
    props: {
        title: {
            type: String,
            required: true
        },
        content: {
            type: String,
            required: true,
            default: "Este post no tiene contenido"
        }
    },
    emits: ['sayhi'],
    setup(props, { emit }) {
        const handleClick = () => {
            emit('sayhi', message.value);
        }
        let message:Ref<string> = ref('');
        return {
            props,
            message,
            handleClick
        }
    }

})
</script>

<style>
.post {
    width: 300px;
    height: 200px;
    border-radius: 10px;
    background-color: antiquewhite;
    margin: 10px;
    padding: 10px;
}
</style>