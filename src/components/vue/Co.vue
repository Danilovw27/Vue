<script setup>

import {ref} from 'vue'

let number = ref(0)
let time = ref(0)
let interval
function add(){
    if(number.value == 0){ 
        interval = setInterval(() => {
            time.value++
        }, 1000)
    }
    if(number.value < 20){
        number.value++;
    }
    if(number.value == 20){
        number.value = 0
    }
    
    if(number.value == 20){
        clearInterval(interval)
    }
}
</script>

<template>
    <div v-show="number > 0" class="float-right mr-80 bg-red-500 rounded inline-block p-2 ">
       Tiempo: {{ time }}
    </div>
    <div @click="add" class="hover:cursor-pointer select-none bg-green-600 text-white py-1 px-2 rounded w-12 text-center mx-auto mt-20">
        {{ number }}
    </div>
    <div v-if="number == 0" class="bg-orange-300 p-2 rounded-md mx-auto w-20 text-center mt-10">
        click 😁
    </div>
    <div v-else class="bg-blue-300 p-2 rounded-md mx-auto w-20 text-center mt-10">
        Go!! 
    </div>
</template>