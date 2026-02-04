<template>
  <div>
      <label v-custom-size:sm>Subtotal:</label>
      <input type="number" v-model="subtotal">
      <h3 v-custom-size-2="50">Total impuestos a pagar: {{ totalvat }} ({{ vat }}%)</h3>
       <h3 v-custom-font.xxl.blue>Total impuestos a pagar 2: {{ totalvat }} ({{ vat }}%)</h3>
  </div>
</template>

<script lang="ts" setup>
 //solucion a ejercicio de impuestos
import {Ref, ref, computed} from 'vue'; 

 const vat = 21;
 let subtotal:Ref<number> = ref(0);
 let totalvat:Ref<number> = computed(() => vat * subtotal.value / 100);
</script>

<style>

</style>