<script setup>
import IconDaw from '../icons/IconDaw.vue';
import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/css'
import 'swiper/css/pagination'
import IconCicle from '../icons/IconCicle.vue';

defineProps({
    list: Object,
})
</script>

<template>
    <div
        class="group bg-white rounded-3xl overflow-hidden flex-1 flex flex-col shadow-lg hover:shadow-2xl transition-all duration-300 border border-zinc-100 max-w-md mx-auto">

        <!-- Слайдер / Изображение -->
        <div class="relative overflow-hidden">
            <swiper class="mySwiper2" :slides-per-view="1" :space-between="10" :loop="true">
                <swiper-slide v-for="item in list.slidesImg" :key="item">
                    <img class="w-full h-64 object-cover transition-transform duration-500 group-hover:scale-105"
                        :src="'/' + item" alt="Тур 1">
                </swiper-slide>
            </swiper>

            <div
                class="absolute top-4 left-4 bg-white/90 backdrop-blur-sm text-xs font-semibold px-3 py-1 rounded-full shadow-sm">
                Популярный тур
            </div>
        </div>

        <!-- Контент -->
        <div class="p-6 flex-1 flex-col justify-between flex">
            <!-- Преимущества -->
            <ul class="space-y-3 mb-6">
                <li v-for="(item, index) in list.advantages" :key="index" class="flex items-start gap-3 text-gray-700">
                    <div class="mt-0.5 text-[#e5c667]">
                        <IconDaw class="w-5 h-5" />
                    </div>
                    <span class="text-[15px] leading-relaxed">{{ item }}</span>
                </li>
            </ul>
            <!-- Цена -->
            <div class="">
                <div class="flex items-baseline gap-1 mb-5">
                    <span class="text-sm text-zinc-500">от</span>
                    <span class="text-3xl font-bold text-zinc-900">{{ list.price }}</span>
                    <span class="text-zinc-500">руб.</span>
                </div>

                <!-- Кнопка -->
                <button
                    class="w-full bg-[#ddb642] hover:bg-[#e5c667] active:bg-[#baa35e] transition-colors text-white font-semibold py-4 rounded-2xl text-base shadow-sm flex items-center justify-center gap-2">
                    <IconCicle />
                    Позвонить
                </button>
            </div>
        </div>
    </div>
</template>