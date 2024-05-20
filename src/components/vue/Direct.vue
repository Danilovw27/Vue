<script setup>
import { ref } from 'vue'

let numeros = ref([1, 2, 3, 4, 5, 6, 7, 8, 9, 10]);
let numeros1 = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
let show = ref(false)

function getEvens() {
    show.value = true;
    return numeros.value.filter(num => num % 2 === 0);
}

function getOdds() {
    show.value = true;
    return numeros.value.filter(num => num % 2 !== 0);
}

const isEven = num => num % 2 === 0;
</script>

<template>
    <div class="bg-slate-400 mx-auto w-96 mt-20 rounded-md">
        <div  class="bg-blue-400 text-center rounded-md w-2/3 mx-auto">
            <h1>Lista de números <br><span v-for="text in numeros1" :key="text" class="text-white"> {{ text }}  </span></h1>
        </div>
        <div v-if="show" class="bg-black text-white text-center mt-6 w-auto mx-auto px-5 rounded-md">
            <span v-for="num in numeros" :key="num" :class="{ 'text-red-500': !isEven(num), 'text-green-500': isEven(num) }"> {{ num }}  </span>
        </div>
        <div class="bg-slate-400 w-2/3 mx-auto mt-10">
            <button @click="numeros = getEvens()" class="bg-green-500">Pares</button>
            <button @click="numeros = getOdds()" class="bg-amber-600 float-right">Impares</button>
        </div> 
    </div>
</template>
