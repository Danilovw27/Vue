<script setup>
import { ref } from 'vue'

let menu = ref([
    { dia: "lunes", desayuno: "papa", almuerzo: "pollo", cena: "caldo" },
    { dia: "martes", desayuno: "huevo", almuerzo: "arroz", cena: "queso" },
    { dia: "miercoles", desayuno: "arepa", almuerzo: "sopa", cena: "fruta" },
    { dia: "jueves", desayuno: "pastel", almuerzo: "ensalada", cena: "burger" },
    { dia: "viernes", desayuno: "torta", almuerzo: "carne", cena: "pan" }
])

let selectedDay = ref(null)
let meal = ref('')

function selectDay(day) {
    selectedDay.value = menu.value.find(d => d.dia === day)
}

function showMeal(type) {
    meal.value = selectedDay.value ? selectedDay.value[type] : ''
}
</script>

<template>
    <div class="bg-slate-500 container mx-auto rounded-md mt-10">
        <div class="p-10 text-center">
            <h1 class="font-semibold text-5xl">Restaurante</h1>
        </div>
        <div class="grid grid-cols-4 mt-10">
            <div class="w-1/2 ml-20">
                <ul class="text-center">
                    <li class="py-4 rounded-md transition duration-300 ease-in-out transform hover:bg-white hover:scale-105">
                        <button @click="selectDay('lunes')">Lunes</button>
                    </li>
                    <li class="py-4 rounded-md transition duration-300 ease-in-out transform hover:bg-white hover:scale-105">
                        <button @click="selectDay('martes')">Martes</button>
                    </li>
                    <li class="py-4 rounded-md transition duration-300 ease-in-out transform hover:bg-white hover:scale-105">
                        <button @click="selectDay('miercoles')">Miércoles</button>
                    </li>
                    <li class="py-4 rounded-md transition duration-300 ease-in-out transform hover:bg-white hover:scale-105">
                        <button @click="selectDay('jueves')">Jueves</button>
                    </li>
                    <li class="py-4 rounded-md mb-10 transition duration-300 ease-in-out transform hover:bg-white hover:scale-105">
                        <button @click="selectDay('viernes')">Viernes</button>
                    </li>
                </ul>
            </div>
            <div class=" ml-32 ">
                <button class="rounded-md bg-slate-200 px-4 py-2 h-11" @click="showMeal('desayuno')">Desayuno</button>
                <div class="h-20 mx-auto mt-6">
                  <span class="ml-4 text-lg rounded-md bg-sky-600 z">{{ meal }}</span>
                </div>
            </div>
            <div class="flex">
                <button class="rounded-md bg-slate-200 px-4 py-2 mx-auto h-10" @click="showMeal('almuerzo')">Almuerzo</button>
            </div>
            <div class="flex">
                <button class="rounded-md bg-slate-200 px-4 py-2 mx-auto h-10" @click="showMeal('cena')">Cena</button>
            </div>
        </div>
    </div>
</template>
