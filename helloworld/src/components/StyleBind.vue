<template>
    <p v-bind:style="{ backgroundColor: '#ccc', color: color }">El mensaje se ha enviado satisfactoriamente.</p>
    <button v-on:click="handleClick()">Cambiar color</button>
</template>

<!-- opcion 1 -->
<script lang="ts" setup>
import { ref } from 'vue';
let color = ref('#fff');
const handleClick = () => { color.value = '#ff0000'; }
</script>


<!-- opcion 2 -->
<!-- <script lang="ts">
    import { defineComponent } from 'vue';
    export default defineComponent({
        data() {
            return {
                color: '#fff'
            }
        },
        methods: {
            handleClick() {
                this.color = '#ff0000';
            }
        }
    });
</script> -->

<!-- opcion 3 -->
<!-- <script lang="ts">
import { defineComponent, ref } from 'vue';
export default defineComponent({
    setup() {
        let color = ref('#fff');
        const handleClick = () => { color.value = '#ff0000'; }
        return { color, handleClick };
    }
});
</script> -->

<style></style>