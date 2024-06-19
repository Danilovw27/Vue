<script setup>
    import {ref} from 'vue'

    let likes = ref(27)
    let dislikes = ref(0)
    let start = ref(false)
    let start1 = ref(false)


    function counter(){
        if(dislikes.value == 0){
            likes.value = 28
        }
        
    }
    function counter2(){
        if(likes.value == 27){
            dislikes.value = 1
            start1.value = true
        }
    }

</script>

<template>
    
    <div class="container w-2/4 shadow-md shadow-black mx-auto p-7" >

        <div class="block w-11/12 mx-auto mb-3">
            <span class="font-semibold text-xl">Historias</span><div class="inline-block float-right bg-blue-500 px-2 py-1 font-semibold hover:cursor-pointer rounded-md text-white">Todas</div>
        </div>
        <div class="grid grid-cols-4 gap-6 w-11/12 mx-auto py-3 h-2/5 select-none">
            <div class="bg-black rounded-2xl h-36">
                <img src="https://media.c5n.com/p/23e83bbc00263816974509a0e7ca37e0/adjuntos/326/imagenes/000/045/0000045267/1200x675/smart/foto-perfil-facebook.png" alt="" class="rounded-2xl h-full border-4 border-pink-700 ">
            </div>
            <div class="bg-red-400 rounded-2xl h-36">
                <img src="https://media.c5n.com/p/23e83bbc00263816974509a0e7ca37e0/adjuntos/326/imagenes/000/045/0000045267/1200x675/smart/foto-perfil-facebook.png" alt="" class="rounded-2xl h-full border-4 border-pink-700">
            </div>
            <div class="bg-slate-400 rounded-2xl h-36">
                <img src="https://media.c5n.com/p/23e83bbc00263816974509a0e7ca37e0/adjuntos/326/imagenes/000/045/0000045267/1200x675/smart/foto-perfil-facebook.png" alt="" class="rounded-2xl h-full border-4 border-slate-400">
            </div>
            <div class="bg-amber-500 rounded-2xl h-36">
                <img src="https://media.c5n.com/p/23e83bbc00263816974509a0e7ca37e0/adjuntos/326/imagenes/000/045/0000045267/1200x675/smart/foto-perfil-facebook.png" alt="" class="rounded-2xl h-full border-4 border-slate-400">
            </div>
        </div>
        <div>
            <div class="block w-11/12 mx-auto my-4 bg-blac select-none">
                <img src="https://hips.hearstapps.com/hmg-prod/images/frases-mejores-fotos-instagram-1663189046.jpg" alt="" class="rounded-full w-16 h-16 inline-block align-middle hover:cursor-pointer"><div class="inline-block ml-2 align-middle"><span class="font-bold ">Mariano perez <br><span class="text-xs text-slate-400"> Hace diez minutos</span></span></div><div class="inline-block float-right mt-8 text-red-700 font-extrabold hover:cursor-pointer italic">Reportar</div>
            </div>
            <div class="mx-auto select-none">
                <img src="https://static.vecteezy.com/system/resources/thumbnails/010/468/057/small_2x/portrait-of-jaguar-free-photo.jpg" alt="" class="mx-auto rounded-md">
            </div>
            <div class="mt-3 block">  
                <svg @click="counter" xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-red-600 hover:cursor-pointer ml-7 inline-block" viewBox="0 0 24 24"><path fill="currentColor" fill-opacity="0" d="M12 20L20.5 11V7L17 5.5L12 7L7 5.5L3.5 7V11L12 20Z"><animate fill="freeze" attributeName="fill-opacity" begin="0.5s" dur="0.5s" values="0;1"/></path><path fill="none" stroke="currentColor" stroke-dasharray="30" stroke-dashoffset="30" stroke-linecap="round" stroke-width="2" d="M12 8C12 8 12 8 12.7578 7C13.6343 5.84335 14.9398 5 16.5 5C18.9853 5 21 7.01472 21 9.5C21 10.4251 20.7209 11.285 20.2422 12C19.435 13.206 12 21 12 21M12 8C12 8 12 8 11.2422 7C10.3657 5.84335 9.06021 5 7.5 5C5.01472 5 3 7.01472 3 9.5C3 10.4251 3.27914 11.285 3.75777 12C4.56504 13.206 12 21 12 21"><animate fill="freeze" attributeName="stroke-dashoffset" dur="0.5s" values="30;0"/></path></svg>
                <div  class="inline-block ml-2 align-middle select-none">{{ likes }}</div>
                <svg @click="counter2" xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 inline-block ml-3 hover:cursor-pointer align-middle mt-2" viewBox="0 0 36 36"><path fill="#f6ddcd" d="M34.956 18.084c0 .503-.12.975-.321 1.404c-1.341 4.326-7.619 4.01-16.549 4.221c-1.493.035-.639 1.798-.115 5.668c.341 2.517-1.282 6.382-4.01 6.382c-4.498 0-.171-3.548-4.148-12.322c-2.125-4.688-6.875-2.062-6.875-6.771V5.948c0-1.833.18-3.595 2.758-3.885C8.195 1.781 7.633 0 11.238 0h18.044a3.337 3.337 0 0 1 3.333 3.334c0 .762-.267 1.456-.698 2.018c1.02.571 1.72 1.649 1.72 2.899c0 .76-.266 1.454-.696 2.015c1.023.57 1.725 1.649 1.725 2.901c0 .909-.368 1.733-.961 2.336a3.311 3.311 0 0 1 1.251 2.581"/><path fill="#dfa994" d="M23.02 14.751h8.604c1.17 0 2.268.626 2.866 1.633a.876.876 0 0 1-1.506.892a1.588 1.588 0 0 0-1.361-.775h-8.81c-.873 0-1.583.71-1.583 1.583s.71 1.583 1.583 1.583H28.7a.875.875 0 0 1 0 1.75h-5.888a3.337 3.337 0 0 1-3.333-3.333c0-1.025.475-1.932 1.205-2.544a3.32 3.32 0 0 1-.998-2.373c0-1.028.478-1.938 1.212-2.549a3.318 3.318 0 0 1 .419-5.08a3.305 3.305 0 0 1-.852-2.204A3.337 3.337 0 0 1 23.798.001h5.484a3.35 3.35 0 0 1 2.867 1.632a.875.875 0 0 1-1.504.894a1.594 1.594 0 0 0-1.363-.776h-5.484c-.873 0-1.583.71-1.583 1.583s.71 1.583 1.583 1.583h6.506c1.17 0 2.27.626 2.867 1.633a.875.875 0 1 1-1.504.894a1.572 1.572 0 0 0-1.363-.777h-7.063a1.585 1.585 0 0 0 0 3.167h8.091a3.35 3.35 0 0 1 2.867 1.632a.875.875 0 0 1-1.504.894a1.573 1.573 0 0 0-1.363-.776H23.02a1.585 1.585 0 0 0 0 3.167"/></svg>
                <div v-if="start1" class="inline-block ml-2 align-middle select-none">{{ dislikes }}</div>
            </div>
        </div>
        <div class="bg-slate-300 shadow-md shadow-black rounded-lg mx-auto py-3 w-11/12 mt-7 flex justify-between">
            <svg xmlns="http://www.w3.org/2000/svg" class="w-10 h-10 inline-block ml-28 hover:cursor-pointer align-middle" viewBox="0 0 24 24"><path fill="currentColor" d="M12 4a4 4 0 0 1 4 4a4 4 0 0 1-4 4a4 4 0 0 1-4-4a4 4 0 0 1 4-4m0 10c4.42 0 8 1.79 8 4v2H4v-2c0-2.21 3.58-4 8-4"/></svg>
            <div class="inline-block bg-white rounded-md "><svg xmlns="http://www.w3.org/2000/svg" class="items-center w-10 h-10 inline-block hover:cursor-pointer align-middle mt-" viewBox="0 0 24 24"><path fill="currentColor" d="M10 20v-6h4v6h5v-8h3L12 3L2 12h3v8z"/></svg></div>
            <svg xmlns="http://www.w3.org/2000/svg" class="w-10 h-10 inline-block float-right hover:cursor-pointer align-middle mr-28" viewBox="0 0 24 24"><path fill="currentColor" d="M9.5 3A6.5 6.5 0 0 1 16 9.5c0 1.61-.59 3.09-1.56 4.23l.27.27h.79l5 5l-1.5 1.5l-5-5v-.79l-.27-.27A6.52 6.52 0 0 1 9.5 16A6.5 6.5 0 0 1 3 9.5A6.5 6.5 0 0 1 9.5 3m0 2C7 5 5 7 5 9.5S7 14 9.5 14S14 12 14 9.5S12 5 9.5 5"/></svg>
        </div>
    </div>


</template>