<template>
    <div class="bg-gray-900 text-gray-100  py-3.5 md:px-24 px-10  shadow md:flex justify-between item-center">
        <div class="flex items-center cursor-pointer">
            <span class="text-blue-500 text-xl mr-1">
                <i class="bi bi-emoji-smile-fill"></i>
            </span>
            <h1 class="text-xl">D74XEz</h1>
        </div>

        <span @click="MenuOpen()" class=" absolute md:hidden right-6 top-1.5 cursor-pointer text-4xl">
            <i :class="[open ? 'bi bi-x' : 'bi bi-list']"></i>
        </span>

        <ul class="md:flex md:items-center md:px-0 px-10 md:pb-0 pb-10 md:static absolute bg-gray-900 md:w-auto w-full top-14 duration-700 ease-in"
        :class="[open ? 'left-0' : 'left-[-100%]']">
            <li class="md:mx-4 md:my-0 my-6" v-for="link in Links">
                <a :href="link.link" class="text-xl hover:text-blue-500">{{link.name}}</a>
            </li>
            
        </ul>
    </div>
</template>
<script>
import { ref} from '@vue/reactivity'
export default {
    
    setup(){
        let open = ref(false)
        let Links = [
        {name : "Home" , link : "#"},
        {name : "About" , link : "#"},
        {name : "Skills" , link : "#"},
        {name : "Portfolio" , link : "#"},
        {name : "Contact" , link : "#"},
        ]

    function MenuOpen(){
        open.value = !open.value
    }

    return{Links,open,MenuOpen}
    
    }
}
</script>
<style>
    
</style>