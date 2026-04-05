<script setup>
import IconDaw from './icons/IconDaw.vue';

</script>

<template>
    <div class="w-full h-200 overflow-y-hidden relative">
        <video class="w-full z-1 absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2" autoplay loop
            muted>
            <source src="/public/preview.mp4" type="video/mp4">
        </video>
        <div class="h-[calc(100%-88px)] mt-22 overflow-y-hidden bottom-0 left-0 w-full relative">
            <div
                class="h-2/1 max-w-170 text-white absolute border-x-3 border-[#cdad4b] -top-14 left-70  z-1 -rotate-8 backdrop-blur-md bg-white/1 py-20 ">
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
                    <h2 class=" ">Встречаем в аэропорту Сочи</h2>
                </div>
                <div class=" w-max overflow-x-hidden rotate-8">
                    <div
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