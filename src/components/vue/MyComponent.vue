<script setup>
import { ref } from 'vue';

const name = "Cristiano Ronaldo";
let counter = ref(0);
let characters = ref([])

function add(){
    counter.value++
    characters.value.push(counter.value)
}
function substract(){
    counter.value--
    console.log(counter)
}
</script>


<template>
    <div class="mx-auto bg-blue-300 max-w-96 rounded py-4 px-6">
        Hola {{ name }}

        <div 
            v-if="counter > 0"
            class="justify-center items-center flex rounded-full size-8 text-white bg-red-600">
            {{ counter }}
        </div>
        <div v-else>
            Barcelona zzz
        </div>
        <div 
            @click="add"
            class="justify-center items-center flex rounded-full size-8 text-white bg-blue-600"
        >
            +
        </div>
        <div 
            @click="substract"
            class="justify-center items-center flex rounded-full size-8 text-white bg-violet-600"
        >
            -
        </div>
        <div
            v-for="(name, index) in characters"
            :key="index"
            class="bg-green-500 mb-1"
        >
            {{ name }}
        </div>
    </div>
</template>