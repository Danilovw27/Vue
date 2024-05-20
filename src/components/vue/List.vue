<script setup>
import { ref } from 'vue'

let tasks = ref(["Hola"])    
let task = ref([''])


function add1 (){
    
    if (task.value.trim() !== '') {  
        tasks.value.push(task.value);  
        task.value = '';  
    }   

}

</script>

<template>
    <div class="bg-slate-500 container mx-auto mt-44 rounded-md w-[500px] h-auto">
        <div class="py-6">
            <h1 class="text-center font-bold text-3xl">Lista de Tareas</h1>
        </div>
        <div class="my-8 w-auto"> 
            <input v-model="task" @keyup.enter="add1" class="p-2 rounded-md ml-32"> <button @click="add1" class="bg-green-400 rounded-md px-3 py-2">+</BUtton>
        </div>
        <div v-for="(task, index) in tasks" :key="index" class="ml-10 font-semibold bg-black text-white w-3/4 mx-auto p-1 rounded-md mb-1">
            {{ task }}
        </div>
        <div>
            
        </div>
    </div>
</template>