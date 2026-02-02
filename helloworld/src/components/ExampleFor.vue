<template>
    <!-- opcion 1: lista simple -->
     
    <!-- 
    <ul>
        <li v-for="country in countries" v-bind:key="country">{{ country }}
        </li>
    </ul>  
    -->
    
    <ul>
        <li v-for="country in countries" v-bind:key="country.code">{{ country.name }}
        </li>
    </ul> 

</template>

<script lang="ts" setup>
import { Ref, ref } from 'vue';
// let countries: Ref<Array<string>> = ref([
//     "Spain",
//     "France",
//     "UK",
//     "Germany",
//     "Italy",
//     "Portugal"
// ])

interface ICountry {
    code: string;
    name: string;
}
let countries:Ref<Array<ICountry>> = ref([
    {
       code:"es",
       name:"Spain",
    },
    {
        code:"fr",
        name:"France"
    },
    {
        code:"en",
        name:"UK"
    },
    {
        code:"it",
        name:"Italy"
    },
    {
        code:"pt",
        name:"Portugal"
    }
])

</script>

<style></style>