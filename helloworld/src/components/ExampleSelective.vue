<template>
    <h1 v-if="age < 18">Eres menor de edad</h1>
    <h1 v-else>Eres mayor de edad</h1>
</template>

<!-- opcion mas larga -->

<!-- 
<script lang="ts">
    import { defineComponent } from 'vue';
    export default defineComponent({
        name: 'ExampleSelective',
        setup() {
            let age = 10;
            return { age }
        }
    });
</script> 
-->

<!-- opcion simple -->
<script lang="ts" setup>
let age = 10;
</script> 



<style scope>

</style>