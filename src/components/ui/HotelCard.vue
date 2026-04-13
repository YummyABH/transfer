<script setup>
import IconDaw from '../icons/IconDaw.vue';
import IconCicle from '../icons/IconCicle.vue';
import IconArrow from '../icons/IconArrow.vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import { ref } from 'vue';
import { Navigation } from 'swiper/modules'
import 'swiper/css'
import 'swiper/css/navigation'

const isOpen = defineModel('isOpen')
const isOpenPreview = ref(false)
const isActivePreview = ref(null)

defineProps({
    list: Object,
})
</script>

<template>
    <div v-show="isOpenPreview" @click="isOpenPreview = false, isActivePreview = null"
        class="w-screen h-screen fixed left-0 top-0 z-100 bg-[#00000074]">
        <img :src="'/' + isActivePreview" alt="Тур 1"
            class="max-w-screen max-h-screen z-101 fixed left-1/2 top-1/2 transform -translate-1/2">
    </div>
    <div
        class="group bg-white rounded-3xl overflow-hidden flex-1 flex flex-col shadow-lg hover:shadow-2xl transition-all duration-300 border border-zinc-100 max-w-md mx-auto">

        <!-- Слайдер / Изображение -->
        <div class="relative overflow-hidden">
            <swiper class="mySwiper2" :slides-per-view="1" :space-between="10" :loop="true" :modules="[Navigation]"
                :navigation="{
                    nextEl: '.custom-next',
                    prevEl: '.custom-prev'
                }">
                <swiper-slide v-for="item in list.slidesImg" :key="item">
                    <img @click="isOpenPreview = true, isActivePreview = item"
                        class="cursor-pointer w-full h-84 object-cover transition-transform duration-500 group-hover:scale-105"
                        :src="'/' + item" alt="Тур 1">
                </swiper-slide>
            </swiper>
            <button
                class="custom-prev absolute left-2 top-1/2 -translate-y-1/2 z-10 w-8 h-12 flex items-center justify-center transition-all duration-200">
                <IconArrow class="cursor-pointer text-white hover:opacity-50 duration-200" />
            </button>

            <button
                class="custom-next absolute right-2 top-1/2 -translate-y-1/2 z-10 w-8 h-12 flex items-center justify-center transition-all duration-200">
                <IconArrow class="cursor-pointer hover:opacity-50 duration-200 text-white rotate-180" />
            </button>

            <div
                class="absolute top-4 left-4 bg-white/90 backdrop-blur-sm text-xs font-semibold px-3 py-1 rounded-full shadow-sm">
                Популярный тур
            </div>
        </div>

        <!-- Контент -->
        <div class="p-6 max-lg:p-3 max-sm:px-1 flex-1 flex-col justify-between flex">
            <!-- Преимущества -->
            <ul class="space-y-4 sm:space-y-3 mb-6">
                <li v-if="list.title" class="flex font-semibold justify-self-center items-start gap-3 text-gray-700">
                    {{ list.title }}
                </li>
                <li v-for="(item, index) in list.advantages" :key="index"
                    class=" items-start sm:flex gap-3 text-gray-700">
                    <div class="mt-0.5 max-sm:pr-2 max-sm:inline-block max-sm:float-left text-[#e5c667]">
                        <IconDaw class="w-5 h-5" />
                    </div>
                    <span class="text-[15px] leading-relaxed">{{ item }}</span>
                </li>
                <li v-if="list.adres" class="text-gray-700 font-base">{{ list.adres }}</li>
                <li v-if="list.subtitle" class="text-gray-700 italic font-light">{{ list.subtitle }}</li>
            </ul>
            <!-- Цена -->
            <div class="">
                <div class="flex items-baseline gap-1 mb-5">
                    <span class="text-sm text-zinc-500">от</span>
                    <span class="text-3xl font-bold text-zinc-900">{{ list.price }}</span>
                    <span class="text-zinc-500">руб.</span>
                </div>

                <!-- Кнопка -->
                <button @click="isOpen = !isOpen"
                    class="text-[15px] w-full cursor-pointer bg-[#ddb642] hover:bg-[#e5c667] active:bg-[#baa35e] transition-colors text-white font-semibold py-4 rounded-2xl text-base shadow-sm flex items-center justify-center gap-2">
                    <IconCicle />
                    Позвонить
                </button>
            </div>
        </div>
    </div>
</template>