<template>
  <div>
    <input type="text" v-model="message">
    <h3>{{ message }}</h3>
    <h3>{{ reverse }}</h3>
  </div>
</template>

<script lang="ts" setup>
//ejemplo con setup 

import { ref, Ref, computed } from 'vue';
let message:Ref<string> = ref('');
const reverse = computed (()=> message.value.split('').reverse().join(''));
        

//Composition API
// import { defineComponent, ref, Ref, computed } from 'vue';

// export default defineComponent({    
//     name: 'ComputedExample',
//     setup(){
//         let message:Ref<string> = ref('');
//         const reverse = computed (()=> message.value.split('').reverse().join(''));
//         return {
//             message,
//             reverse
//         }
//     }
// })

// ejemplo con options API
// import { defineComponent } from 'vue';

// export default defineComponent({    
//     name: 'ComputedExample',
//     data(){
//         return {
//             message: ''
//         }
//     },
//     computed:{
//         reverse():string{
//             return this.message.split('').reverse().join('');
//         }
//     }
// })





</script>

<style>

</style>