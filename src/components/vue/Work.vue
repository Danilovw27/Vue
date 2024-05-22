<script setup>
import {ref} from 'vue'

let numeros = ref([1,2,3,4,5,6,7,8,9,10])
let s = ref([1,2,3,4,5,6,7,8,9,10])


function even(){
    return numeros.value.filter(num => num % 2 === 0)
}
function odd(){
    return numeros.value.filter(num => num % 2 !== 0)
}
const par = num => num % 2 === 0

</script>

<template>

    <div class="bg-slate-400 container mx-auto w-3/5 mt-28 rounded-md">
        <h1 class="text-center font-semibold text-3xl pt-10" >Lista de numeros</h1>
        <h1  class="text-center pt-10 space-x-4" ><span v-for="text in s" :key="text" class="text-white"> {{ text }}  </span></h1>
        <div class="grid grid-cols-2 my-16 h pb-14">
            <div  @click="numeros = even()"  class="bg-white rounded-md w-1/3 mx-auto hover:cursor-pointer select-none" >
                <h1 class="text-center py-1" >Pares</h1>
                <h1 v-show="numeros[0] == 2 " v-for="num in numeros" key="num" class="text-center py-1" :class="{'text-green-500' : par(num)}" >{{ num }}</h1>
            </div>
            <div @click="numeros = odd()" class="bg-white rounded-md w-1/3 mx-auto hover:cursor-pointer select-none" >
                <h1 class="text-center py-1" >impares</h1>
                <h1 v-if="numeros[1] == 3" v-for="num in numeros" key="num" class="text-center py-1" :class="{'text-red-500' : !par(num)}" >{{ num }}</h1>
            </div>
        </div>


    </div>



</template>