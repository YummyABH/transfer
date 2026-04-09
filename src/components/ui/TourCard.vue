<script setup>
import IconDaw from '../icons/IconDaw.vue';

defineProps({
    img: String,
    title: String,
    list: Object
})

</script>

<template>
    <div class="relative w-full h-96 lg:h-96 group">
        <div class="absolute left-0 top-4">
            <h2
                class=" z-2 pl-4 text-base py-2 pr-4 relative text-black before:-right-1 after:-bottom-1.25 after:absolute after:w-1.5 after:-right-1.5 after:h-3.25 bg-white after:bg-white before:-top-1 box-border before:w-1.5 before:bg-white before:absolute before:h-12 before:-rotate-8 inline-block border-y-5  font-semibold border-white">
                {{ title }}
            </h2>
        </div>
        <img class="absolute z-0 top-0 left-0 w-full h-full object-cover" :src="'/' + img" alt="Tour 1">
        <div
            class="absolute z-1 top-0 left-0 w-full h-full bg-white/1 backdrop-blur-sm opacity-0 transition-opacity duration-300 group-hover:opacity-100 max-xl:opacity-100">
            <ul class="grid grid-cols-1 pt-28 gap-y-1">
                <li v-for="(item, index) in list.advantages" :key="index"
                    class="px-4 border-y border-y-white relative text-white flex gap-x-2 py-1 max-w-90 bg-[#e5c667]">
                    <span
                        class="absolute -left-8 top-0 z-20 inline-block border-16 border-transparent border-r-[#e5c667]"></span>
                    <IconDaw />
                    <span>{{ item }}</span>
                </li>
                <div class="py-1 mt-2 px-2 bg-white w-max"><span class="font-medium">Цена:</span> от {{ list.price }}
                    руб.
                </div>
                <div
                    class="mt-2 px-6 py-2 border-2 border-[#e5c667] border-l-0 text-white w-max hover:bg-[#e5c667] duration-200 cursor-pointer">
                    Позвонить</div>
            </ul>
        </div>
    </div>
</template>