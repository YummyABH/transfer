<script setup>
import { ref } from 'vue';
import IconDaw from '../icons/IconDaw.vue';
import IconWhatsapp from '../icons/IconWhatsapp.vue';
import IconTelegramm from '../icons/IconTelegramm.vue';

defineProps({
    img: String,
    title: String,
    list: Object
})

const isOpen = defineModel('isOpen')
const isOpenLink = ref(false)
</script>

<template>
    <div v-show="isOpenLink" @click="isOpenLink = false"
        class="fixed w-screen h-screen bg-black/70 flex justify-center items-center top-1/2 left-1/2 z-100 transform -translate-1/2">
        <div class="bg-white relative border-[#e5c667] w-max  border px-10 pb-6 pt-10 ">
            <button @click="closeModal"
                class="cursor-pointer absolute top-2 right-2 w-8 h-8 flex items-center justify-center text-gray-400 hover:text-gray-600 transition-colors">
                ✕
            </button>
            <div class="flex gap-x-2">
                <a href="tg:@gostevoi_dom_delfine989" target="_blank">
                    <div class="bg-[#0084c6] duration-200 cursor-pointer rounded-lg flex p-2 
                                    transition-all 
                                    hover:bg-[#006a9e]
                                    hover:shadow-[inset_0_4px_10px_rgba(0,0,0,0.35)]
                                    active:scale-95 
                                    active:shadow-[inset_0_8px_16px_rgba(0,0,0,0.5)]">
                        <IconTelegramm />
                    </div>
                </a>
                <a href="https://wa.me/message/5VZS6ZUKG5SSE1" target="_blank">
                    <div class="bg-[#01e675] duration-200 cursor-pointer rounded-lg flex p-2 
                                    transition-all 
                                    hover:bg-[#70d850]
                                    hover:shadow-[inset_0_4px_10px_rgba(0,0,0,0.35)]
                                    active:scale-95 
                                    active:shadow-[inset_0_8px_16px_rgba(0,0,0,0.5)]">
                        <IconWhatsapp />
                    </div>

                </a>
                <a href="https://max.ru/u/f9LHodD0cOJWv4FpXUT5fnw0AlV0XkGw8P7eq1lEXDadg6m1PJNAu9eTCxU" target="_blank">
                    <img class="w-10 h-10" src="/max.png" alt="">
                </a>
            </div>
            <div class="mt-4 hover:text-zinc-500 duration-200">
                <a href="tel:+79409626290">+7 (940) 962-62-90</a>
            </div>
        </div>
    </div>
    <div class="relative w-full h-104 lg:h-96 group">
        <div class="absolute left-0 top-4">
            <h3
                class=" z-2 pl-4  py-2 pr-4 relative text-black before:-right-1 after:-bottom-1.25 after:absolute after:w-1.5 after:-right-1.5 after:h-3.25 bg-white after:bg-white before:-top-1 box-border before:w-1.5 before:bg-white before:absolute before:h-12 before:-rotate-8 inline-block border-y-5  font-semibold border-white">
                {{ title }}
            </h3>
        </div>
        <img class="absolute z-0 top-0 left-0 w-full h-full object-cover" :src="'/' + img" alt="Tour 1">
        <div
            class="absolute z-1 top-0 left-0 w-full h-full bg-white/1 backdrop-blur-sm opacity-0 transition-opacity duration-300 group-hover:opacity-100 max-xl:opacity-100">
            <ul class="grid grid-cols-1 pt-28 gap-y-1">
                <li v-for="(item, index) in list.advantages" :key="index"
                    class="px-4 border-y border-y-white relative text-black flex gap-x-2 py-1 max-w-90 bg-white">
                    <IconDaw class="text-[#e5c667]" />
                    <span>{{ item }}</span>
                </li>
                <div class="py-1 mt-2 px-2 bg-white w-max"><span class="font-medium">Цена:</span> от {{ list.price }}
                    руб.
                </div>
                <div class="flex gap-x-2 max-sm:mx-auto ">
                    <div @click="isOpen = !isOpen"
                        class="mt-2 px-6 max-[360px]:px-3 py-2 border-2 border-[#e5c667] text-white w-max hover:bg-[#e5c667] duration-200 cursor-pointer">
                        Оставить заявку</div>
                    <div @click="isOpenLink = !isOpenLink"
                        class=" mt-2 px-6 py-2 max-[360px]:px-3 border-2 border-[#e5c667] text-white w-max hover:bg-[#e5c667] duration-200 cursor-pointer">
                        Позвонить</div>
                </div>
            </ul>
        </div>
    </div>
</template>