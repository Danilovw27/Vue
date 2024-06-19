<script setup>
    import {ref} from 'vue'

    let show = ref(false)
    let show1 = ref(false)

    let mensajes = ref([ 
        "Marcos perez","Hola","como estás?"
        ])

    let mensajes2 =  ref([ 
        "Pedro","Hola","como estás?","te ves bien"
        ])    

    function page(){
        show.value = true
        show1.value = false
    } 
    function page1(){
        show1.value = true
        show.value = false
    }        


</script>

<template>

<div class="bg-slate-800 container mx-auto rounded-md p-2 block w-4/5 ">
    
    <div class="grid grid-cols-4 w-[99%] mx-auto rounded-md h-[520px]" style="grid-template-columns: 1fr 3fr 5fr 3fr">
        <div class="bg-slate-950 w-[98%] rounded-l-md inline-block">
            <img src="https://www.mundodeportivo.com/urbantecno/hero/2022/06/foto-de-perfil-2.jpg?width=1200" alt="" class="w-20 h-16 rounded-2xl mx-auto mt-5">
            <h1 class="text-lg text-slate-600 font-bold text-center">Perfil</h1>
        </div>
        <div class="bg-slate-700">
            <h1 class="ml-8 mt-4">Tendencias</h1>
            <h1 class="ml-5">#Hola</h1>
            <h1 class="ml-5">#Ocaña</h1>
            <h1 class="ml-5">#Ocaña</h1>
            <H1 class="ml-5 mt-32 text-gray-200">Mensajes Directos</H1>
            <div @click="page" class="bg-slate-500 rounded-md w-11/12 py-1 mx-auto mt-3 hover:cursor-pointer">
                <img src="https://upload.wikimedia.org/wikipedia/commons/1/1e/PERFIL-FACEBOOK-2.png" alt="" class="w-10 h-10 rounded-full inline-block align-top mt-1 ml-1 "><h1 class="inline-block ml-3">Marcos Perez <br> <span class="text-xs">Hace 10 minutos</span></h1>
            </div>
            <div @click="page1" class="bg-slate-500 rounded-md w-11/12 py-1 mx-auto mt-2 hover:cursor-pointer ">
                <img src="https://upload.wikimedia.org/wikipedia/commons/1/1e/PERFIL-FACEBOOK-2.png" alt="" class="w-10 h-10 rounded-full inline-block align-top mt-1 ml-1 "><h1 class="inline-block ml-3">Marcos Perez <br> <span class="text-xs">Hace 10 minutos</span></h1>
            </div>
        </div>
        <div class="bg-slate-500">
            <div v-if="show">
                <div class="ml-10 text-slate-300 text-xl my-7 ">{{ mensajes[0] }}</div>
                    <div class="bg-slate-700 rounded-md w-11/12 py-3 mx-auto mt-3 hover:cursor-pointer text-slate-200 ">
                        <span class="ml-3" >{{ mensajes[1] }}</span>
                    </div>
                <div class="bg-slate-700 rounded-md w-11/12 py-3 mx-auto mt-3 hover:cursor-pointer text-slate-200 ">
                    <span class="ml-3" >{{ mensajes[2] }}</span>
                </div>
            </div>
            <div v-if="show1">
                <div class="ml-10 text-slate-300 text-xl my-7 ">{{ mensajes2[0] }}</div>
                    <div class="bg-slate-700 rounded-md w-11/12 py-3 mx-auto mt-3 hover:cursor-pointer text-slate-200 ">
                        <span class="ml-3" >{{ mensajes2[1] }}</span>
                    </div>
                <div class="bg-slate-700 rounded-md w-11/12 py-3 mx-auto mt-3 hover:cursor-pointer text-slate-200 ">
                    <span class="ml-3" >{{ mensajes2[2] }}</span>
                </div>
                <div class="bg-slate-700 rounded-md w-11/12 py-3 mx-auto mt-3 hover:cursor-pointer text-slate-200 ">
                    <span class="ml-3" >{{ mensajes2[3] }}</span>
                </div>
            </div>
        </div>

        <div class="bg-slate-700 rounded-r-md">
            Publicidad 
            <img src="https://www.hubspot.com/hubfs/media/ejemplospublicidadproductobk.jpeg" alt="">
            <img src="https://www.comunicarseweb.com/sites/default/files/styles/galeria_noticias/public/biblioteca/images//1437506486_Fanta-Fanta-Taste-Grafica-1.jpg?itok=BQrq6hlk" alt="">
        </div>

    </div>
</div>

</template>