<script setup>
import { ref } from 'vue';

const name = "pepito"
let counter = ref(5)

let characters = ref([])

function add(){
    counter.value++
    characters.value.push(counter.value)
}
function rest(){
    counter.value--
    console.log(counter)
}
</script>

<template>
    <div class="bg-blue-300 max-w-96 rounded py-4 px-6 mx-auto text-center">
        Hola {{ name }}

        <div
        v-if="counter>0"
        class="bg-red-600 text-white size-8 rounded-full flex items-center justify-center">
            {{ counter }}
        </div>
        <div v-else>
            Nadie te quiere :(
        </div>
        <div class="flex">
            <div 
            @click="add()"
            class="bg-blue-600 text-white size-8 rounded-full flex items-center justify-center cursor-pointer">
                +
            </div>
            <div 
            @click="rest()"
            class="bg-blue-600 text-white size-8 rounded-full flex items-center justify-center cursor-pointer">
                -
            </div>
        </div>
    </div>
    <div 
    v-for="(name, index) in characters"
    :key="index"
    class="bg-green-500 mb-1">
    {{ name }}
    </div>
</template>
