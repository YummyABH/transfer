<script setup>
import IconDaw from './icons/IconDaw.vue';

const isOpen = defineModel('isOpen')
</script>

<template>
    <div class="w-full h-200 max-sm:h-160 overflow-y-hidden relative overflow-hidden" id="transfer">
        <div class="w-full overflow-hidden">
            <video class="absolute overflow-hidden inset-0 w-full h-full object-cover z-[-1]" autoplay loop muted
                playsinline>

                <source src="/preview.mp4" type="video/mp4">
            </video>
        </div>

        <div
            class="lg:hidden max-sm:px-0 max-sm:py-5 max-w-140 px-10 py-10 rounded-2xl mx-auto translate-y-1/3  text-white backdrop-blur-md">
            <h1 class="text-center max-sm:text-xl text-2xl  text-white mb-10">Лицензированный трансфер
                Республики
                Абхазия.
            </h1>
            <div class="flex gap-x-4 border-y max-sm:px-5 max-sm:text-sm px-10 text-lg py-3 ">
                <IconDaw class="mb-0.75" />
                <h2 class="">VIP поездки по Абхазии</h2>
            </div>
            <div class="flex gap-x-4 border-y max-sm:px-5 max-sm:text-sm px-10 text-lg py-3">
                <IconDaw class="mb-0.75" />
                <h2 class="">Встречаем в аэропорту Сочи, Ж/Д вокзале Адлера</h2>
            </div>
            <div class="flex gap-x-4 border-y max-sm:px-5 max-sm:text-sm px-10 text-lg py-3">
                <IconDaw />
                <h2 class="">Встречаем на границе</h2>
            </div>
            <div class="flex gap-x-4 border-y max-sm:px-5 max-sm:text-sm px-10 text-lg py-3">
                <IconDaw />
                <h2 class=" ">Встречаем в аэропорту Сухум</h2>
            </div>
            <div class="w-max overflow-x-hidden flex justify-self-center mt-6">
                <div
                    class=" box-border border-3 px-10 py-3  border-white  hover:border-[#ffde7ba4]  hover:bg-[#ffde7ba4] duration-200 cursor-pointer">
                    <span @click="isOpen = !isOpen">
                        Оставить заявку
                    </span>
                </div>
            </div>
        </div>

        <div
            class="overflow-hidden max-lg:hidden h-[calc(100%-88px)] mt-22 overflow-y-hidden bottom-0 left-0 w-full relative">
            <div
                class="h-2/1 max-w-170  text-white absolute border-x-3 border-[#cdad4b] -top-14 left-70 max-lg:left-1/2 max-lg:-translate-x-1/2 z-1 -rotate-8 backdrop-blur-md bg-white/1 py-20 ">
                <h1 class="rotate-8 px-10 text-center text-3xl mt-10 text-white mb-22">Лицензированный трансфер
                    Республики
                    Абхазия.
                </h1>
                <div class="rotate-8 flex gap-x-6 border-y px-10 text-xl py-4">
                    <IconDaw class="mb-0.75" />
                    <h2 class="">VIP поездки по Абхазии</h2>
                </div>
                <div class="rotate-8 flex gap-x-6 border-y px-10 text-xl py-4">
                    <IconDaw class="mb-0.75" />
                    <h2 class="">Встречаем в аэропорту Сочи, Ж/Д вокзале Адлера</h2>
                </div>
                <!-- <div class=" flex gap-x-6 rotate-8 px-10 border-y text-xl py-4">
                    <IconDaw />
                    <h2 class="">Встречаем на Ж/Д вокзале Адлера
                    </h2>
                </div> -->
                <div class="flex gap-x-6  rotate-8 px-10 border-y text-xl py-4">
                    <IconDaw />
                    <h2 class="">Встречаем на границе</h2>
                </div>
                <div class="flex gap-x-6 rotate-8 px-10 border-y text-xl py-4 mb-10">
                    <IconDaw />
                    <h2 class=" ">Встречаем в аэропорту Сухум</h2>
                </div>
                <div class=" w-max overflow-x-hidden rotate-8">
                    <div @click="isOpen = !isOpen"
                        class="relative box-border border-3 px-10 py-3 ml-10 border-white  hover:border-[#ffde7ba4]  hover:bg-[#ffde7ba4] duration-200 cursor-pointer">
                        <span>
                            Оставить заявку
                        </span>
                    </div>
                </div>

            </div>
        </div>
    </div>
</template>