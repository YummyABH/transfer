<script setup>
import { ref, computed } from 'vue'
import IconPerson from '@/components/icons/IconPerson.vue';


const props = defineProps({
    img: String,
    cars: Array,
    passengers: Number
})

const selectedTitle = ref(props.cars[0]?.title || '')

const carTitle = computed(() => 'Автомобиль · Премиум комфорт')

const description = computed(() => '• Эксклюзивное обслуживание от Аэропорта Сочи. <br/>• Железнодорожного вокзала Адлер. <br/>• По указанному адресу. <br/>• Трансфер на элитном автомобиле седан класса Lux с индивидуальным подходом.')

const currentPrice = computed(() => {
    const selectedCar = props.cars.find(car => car.title === selectedTitle.value)
    return selectedCar ? selectedCar.price : '0 ₽'
})
</script>

<template>
    <div
        class="group flex max-w-7xl  px-10 max-md:px-5 mx-auto bg-linear-to-br from-[#ffe9a0] to-[#0d0d0d] rounded-2xl overflow-hidden shadow-[0_20px_40px_rgba(0,0,0,0.3),0_0_0_1px_rgba(255,215,0,0.1)] transition-all duration-500 ease-[cubic-bezier(0.4,0,0.2,1)] hover:-translate-y-1 hover:shadow-[0_24px_48px_rgba(0,0,0,0.4),0_0_0_1px_rgba(229,198,103,0.3)]">
        <div class="relative flex-[0_0_40%] overflow-hidden">
            <div class="h-full flex items-center">
                <img class="w-full  object-cover transition-transform duration-600 ease-in-out group-hover:scale-105"
                    :src="`/public/${img}`" :alt="carTitle">
            </div>
            <div
                class="absolute top-5 left-5 bg-linear-to-br from-[#e5c667] to-[#d4af37] py-1.5 px-3.5 rounded-full shadow-md">
                <span class="text-xs font-semibold tracking-wide text-[#1a1a1a] uppercase">Премиум класс</span>
            </div>
        </div>

        <div class="flex-1 p-7 md:p-8 flex flex-col">
            <div class="flex justify-between items-start mb-5 flex-wrap gap-3">
                <h3 class="text-2xl md:text-2xl font-semibold text-white tracking-tight leading-tight m-0">{{ carTitle
                    }}</h3>
                <div class="flex items-center gap-2 bg-black/58 py-1.5 px-3.5 rounded-full backdrop-blur-[10px]">
                    <IconPerson class="w-4.5 h-4.5 text-[#e5c667]" />
                    <span class="text-sm font-medium text-[#e5c667]">{{ passengers }} пассажира</span>
                </div>
            </div>

            <p class="text-sm leading-relaxed text-white/70 mb-6 flex-1" v-html="description">

            </p>

            <div class="mb-7">
                <select v-model="selectedTitle"
                    class=" bg-black/5! border! border-[#e5c667]/30! rounded-xl! py-3! px-4! text-sm! text-white! cursor-pointer! transition-all! duration-300! outline-none! hover:bg-white/8! hover:border-[#e5c667]/60! focus:border-[#e5c667]! focus:shadow-[0_0_0_3px_rgba(229,198,103,0.1)]!">
                    <option v-for="item in cars" :key="item.title" :value="item.title" class="bg-[#7e7557]">
                        {{ item.title }}
                    </option>
                </select>
            </div>

            <div
                class="flex justify-between gap-5 pt-5 border-t border-white/10 md:flex-row flex-col md:items-center items-stretch">
                <div class="flex flex-col gap-1">
                    <span class="text-xs text-white/50 tracking-wide uppercase">Стоимость</span>
                    <div class="flex items-baseline gap-0.5">
                        <span class="text-[28px] font-bold text-[#e5c667] leading-none">{{ currentPrice }}</span>
                        <span class="text-base font-medium text-[#e5c667]">₽</span>
                    </div>
                </div>

                <button
                    class="bg-transparent border-[1.5px] border-[#e5c667]/50 rounded-full py-3 px-7 md:px-7 flex items-center gap-2.5 cursor-pointer transition-all duration-300 text-sm font-medium text-white whitespace-nowrap hover:bg-[#e5c667] hover:border-[#e5c667] hover:text-[#1a1a1a] hover:translate-x-1 justify-center">
                    <span>Заказать трансфер</span>
                    <svg class="w-5 h-5 transition-transform duration-300 group-hover:translate-x-1" viewBox="0 0 24 24"
                        fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M5 12H19M19 12L13 6M19 12L13 18" stroke="currentColor" stroke-width="2"
                            stroke-linecap="round" stroke-linejoin="round" />
                    </svg>
                </button>
            </div>
        </div>
    </div>
</template>
