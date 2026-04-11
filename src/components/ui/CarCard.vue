<script setup>
import IconPerson from '@/components/icons/IconPerson.vue';
import { computed, ref } from 'vue';

const props = defineProps({
    img: String,
    cars: Array,
    passengers: Number,
    mark: String
})

const isOpen = defineModel('isOpen')
const selectedTitle = ref(props.cars[0].title)
const description = computed(() => `• Забираем от Аэропорта Сочи. <br/>• Железнодорожного вокзала Адлер. <br/>• По указанному адресу. <br/>• Трансфер на комфортном автомобиле ${props.mark} - посадка до ${props.passengers}-х мест.`)

const currentPrice = computed(() => {
    const selectedItem = props.cars.find(item => item.title === selectedTitle.value)
    return selectedItem ? selectedItem.price : 0
})
</script>

<template>
    <div class="shadow-2xl flex flex-col lg:flex-row">

        <!-- Левая часть с фото -->
        <div class="w-full lg:w-130 border-b-3 lg:border-b-0 lg:border-r-3 border-[#000000]">
            <img class="max-lg:aspect-3/2 max-lg:px-0 px-10 py-8 lg:py-0 w-full h-auto object-contain" :src="`/${img}`"
                alt="">
        </div>

        <!-- Правая часть с информацией -->
        <div class="flex flex-col flex-1">

            <h3 class="px-4 py-3 lg:py-2 text-xl font-medium">
                Автомобиль {{ mark }} до {{ passengers }} мест
            </h3>

            <div class="inline-block  max-lg:text-sm max-lg:pt-0 text-base px-4 py-4 flex-1 leading-relaxed"
                v-html="description">
            </div>

            <!-- Select -->
            <div class="">
                <select v-model="selectedTitle" class="w-full! lg:w-max! bg-zinc-600! py-2! lg:py-1! text-white! px-4!">
                    <option v-for="item in cars" :key="item.title" :value="item.title">
                        {{ item.title }}
                    </option>
                </select>
            </div>

            <!-- Нижняя панель с ценой и кнопкой -->
            <div class="flex items-center border-t bg-[#000000] px-4 py-4 mt-auto">
                <div
                    class=" flex justify-between w-full flex-col md:flex-row gap-4 md:gap-0 items-start md:items-center">

                    <!-- Цена + Количество мест -->
                    <div class="max-md:justify-between max-md:w-full flex items-center flex-wrap gap-x-4">
                        <div class="flex items-center gap-x-1">
                            <span class="text-xl max-lg:text-lg font-medium text-white">Цена:</span>
                            <span class="text-xl max-lg:text-lg font-bold text-white">{{ currentPrice }}</span>
                        </div>
                        <div class="flex items-center gap-x-2">
                            <IconPerson class="text-white" />
                            <span class="text-xl text-white font-semibold">{{ passengers }}</span>
                        </div>
                    </div>

                    <!-- Кнопка "Заказать" -->
                    <div @click="isOpen = !isOpen" class="box-border max-md:mx-auto max-lg:px-3 max-lg:py-1 border-3 px-6 py-2.5 text-white  
                            border-white hover:border-[#ffde7ba4] hover:bg-[#ffde7ba4] 
                            duration-200 cursor-pointer text-center whitespace-nowrap">
                        <span>Заказать</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>