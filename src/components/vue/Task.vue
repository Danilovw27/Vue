<script setup>
import { ref } from 'vue';

let tareas = ref([
    { dia: "lunes", tasks: [{ description: "Ir al gimnasio" }, { description: "Correr" }] },
    { dia: "martes", tasks: [{ description: "Estudiar Vue.js" }] },
    { dia: "miercoles", tasks: [{ description: "Hacer la compra" }] },
    { dia: "jueves", tasks: [{ description: "Llamar a mamá" }] },
    { dia: "viernes", tasks: [{ description: "Salir a correr" }] },
]);

let selectedDay = ref(null);
let newTask = ref('');

function show(day) {
    selectedDay.value = day;
}

function addTask() {
    if (selectedDay.value && newTask.value.trim() !== '') {
        const dayTasks = tareas.value.find(d => d.dia === selectedDay.value);
        if (dayTasks) {
            dayTasks.tasks.push({ description: newTask.value });
            newTask.value = '';
        }
    }
}

</script>




<template>
    <div class="bg-slate-500 container mx-auto mt-28 rounded-md">
        <div class="text-center">
            <h1 class="p-16 font-semibold text-3xl">Planificador de tareas diarias</h1>
        </div>

        <div class="grid grid-cols-5 gap-4">
            <div class="bg-red-500 rounded-md h-96 p-4">
                <button @click="show('lunes')" class="h-16 my-4 w-full transition duration-300 ease-in-out transform hover:bg-white hover:scale-105 rounded-md">Lunes</button>
                <input v-if="selectedDay === 'lunes'" v-model="newTask" type="text" placeholder="Agregar Tarea" class="rounded-md my-auto p-1 w-2/3">
                <button v-if="selectedDay === 'lunes'" @click="addTask" class="px-2 bg-slate-400 rounded-md ml-2">+</button>
                <div v-if="selectedDay === 'lunes'" class="bg-white w-full mx-auto mt-5 p-2 rounded-md">
                    <ul>
                        <li v-for="task in tareas.find(d => d.dia === 'lunes').tasks" :key="task.description">{{ task.description }}</li>
                    </ul>
                </div>
            </div>
            <div class="bg-slate-700 rounded-md h-96 p-4">
                <button @click="show('martes')" class="h-16 my-4 w-full transition duration-300 ease-in-out transform hover:bg-white hover:scale-105 rounded-md">Martes</button>
                <input v-if="selectedDay === 'martes'" v-model="newTask" type="text" placeholder="Agregar Tarea" class="rounded-md my-auto p-1 w-2/3">
                <button v-if="selectedDay === 'martes'" @click="addTask" class="px-2 bg-slate-400 rounded-md ml-2">+</button>
                <div v-if="selectedDay === 'martes'" class="bg-white w-full mx-auto mt-5 p-2 rounded-md">
                    <ul>
                        <li v-for="task in tareas.find(d => d.dia === 'martes').tasks" :key="task.description">{{ task.description }}</li>
                    </ul>
                </div>
            </div>
            <div class="bg-green-500 rounded-md h-96 p-4">
                <button @click="show('miercoles')" class="h-16 my-4 w-full transition duration-300 ease-in-out transform hover:bg-white hover:scale-105 rounded-md">Miércoles</button>
                <input v-if="selectedDay === 'miercoles'" v-model="newTask" type="text" placeholder="Agregar Tarea" class="rounded-md my-auto p-1 w-2/3">
                <button v-if="selectedDay === 'miercoles'" @click="addTask" class="px-2 bg-slate-400 rounded-md ml-2">+</button>
                <div v-if="selectedDay === 'miercoles'" class="bg-white w-full mx-auto mt-5 p-2 rounded-md">
                    <ul>
                        <li v-for="task in tareas.find(d => d.dia === 'miercoles').tasks" :key="task.description">{{ task.description }}</li>
                    </ul>
                </div>
            </div>
            <div class="bg-red-950 rounded-md h-96 p-4">
                <button @click="show('jueves')" class="h-16 my-4 w-full transition duration-300 ease-in-out transform hover:bg-white hover:scale-105 rounded-md">Jueves</button>
                <input v-if="selectedDay === 'jueves'" v-model="newTask" type="text" placeholder="Agregar Tarea" class="rounded-md my-auto p-1 w-2/3">
                <button v-if="selectedDay === 'jueves'" @click="addTask" class="px-2 bg-slate-400 rounded-md ml-2">+</button>
                <div v-if="selectedDay === 'jueves'" class="bg-white w-full mx-auto mt-5 p-2 rounded-md">
                    <ul>
                        <li v-for="task in tareas.find(d => d.dia === 'jueves').tasks" :key="task.description">{{ task.description }}</li>
                    </ul>
                </div>
            </div>
            <div class="bg-amber-600 rounded-md h-96 p-4">
                <button @click="show('viernes')" class="h-16 my-4 w-full transition duration-300 ease-in-out transform hover:bg-white hover:scale-105 rounded-md">Viernes</button>
                <input v-if="selectedDay === 'viernes'" v-model="newTask" type="text" placeholder="Agregar Tarea" class="rounded-md my-auto p-1 w-2/3">
                <button v-if="selectedDay === 'viernes'" @click="addTask" class="px-2 bg-slate-400 rounded-md ml-2">+</button>
                <div v-if="selectedDay === 'viernes'" class="bg-white w-full mx-auto mt-5 p-2 rounded-md">
                    <ul>
                        <li v-for="task in tareas.find(d => d.dia === 'viernes').tasks" :key="task.description">{{ task.description }}</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>



