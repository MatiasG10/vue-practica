<template>
    <div class="post">
        <h3>{{ props.title }}</h3>
        <p>{{ props.content }}</p>
        <input type="text" v-model="message">

        <button @click="handleClick()">Di hola</button>
    </div>
</template>

<script lang="ts" setup>
//opcion con setup script y defineProps/defineEmits

import { Ref, ref} from 'vue';

// en el video se agrega esto import {defineProps, defineEmits, Ref, ref} from 'vue';
// pero defineProps y defineEmits no se usan como import normales, sino como funciones dentro del setup script
//El error que estás viendo es normal. En Vue 3 con <script setup>, defineProps y defineEmits son macros del compilador 
// y no necesitan ser importados. Solo necesitas importar Ref y ref.


const props = defineProps({
    title: String, 
    content: String
});

const emit = defineEmits(['sayhi']);

const handleClick = () => {
    emit('sayhi', message.value);
}
let message:Ref<string> = ref('');


//opcion con defineProps y defineEmits , sin el setup
// import { defineComponent, Ref, ref } from 'vue';
// export default defineComponent({
//     name: 'PostDetail',
//     props: {
//         title: {
//             type: String,
//             required: true
//         },
//         content: {
//             type: String,
//             required: true,
//             default: "Este post no tiene contenido"
//         }
//     },
//     emits: ['sayhi'],
//     setup(props, { emit }) {
//         const handleClick = () => {
//             emit('sayhi', message.value);
//         }
//         let message:Ref<string> = ref('');
//         return {
//             props,
//             message,
//             handleClick
//         }
//     }

// })


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