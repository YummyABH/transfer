<script setup>
import ContentContainer from './ContentContainer.vue'
import CarCard from './ui/CarCard.vue'
const isOpen = defineModel('isOpen')

const cars = [
    [
        {
            price: 4000,
            title: 'Гагра',
        },
        {
            price: 5000,
            title: 'Пицунда',
        },
        {
            price: 5500,
            title: 'Гудаута',
        },
        {
            price: 6000,
            title: 'Новый Афон',
        },
        {
            price: 7000,
            title: 'Сухум',
        },
        {
            price: 10000,
            title: 'Очамчира',
        },
        {
            price: 12000,
            title: 'Ткурчал',
        },
        {
            price: 12000,
            title: 'Гал',
        },
    ],
    [
        {
            price: 5000,
            title: 'Гагра',
        },
        {
            price: 6000,
            title: 'Пицунда',
        },
        {
            price: 6500,
            title: 'Гудаута',
        },
        {
            price: 7000,
            title: 'Новый Афон',
        },
        {
            price: 8000,
            title: 'Сухум',
        },
        {
            price: 11000,
            title: 'Очамчира',
        },
        {
            price: 13000,
            title: 'Ткурчал',
        },
        {
            price: 13000,
            title: 'Гал',
        },
    ],
]
</script>

<template>
    <div class="w-full py-20" id="car">
        <h2
            class="mb-20 max-md:pl-20 max-lg:mb-12 max-lg:pl-40 pl-104 py-2 pr-18 relative before:-right-1 after:-bottom-1.25 after:absolute after:w-1.5 after:-right-1.5 after:h-3.25 bg-[#e5c667] text-white after:bg-[#e5c667] before:-top-1 box-border before:w-3.25 before:bg-[#e5c667] before:absolute before:h-14 before:-rotate-8 inline-block border-y-5 text-2xl font-semibold border-[#e5c667]">
            Транспорт
        </h2>
        <ContentContainer>
            <div class="flex flex-col max-md:flex-col max-lg:grid max-lg:grid-cols-2 max-sm:flex gap-10.5">
                <CarCard v-model:isOpen="isOpen" :mark="'седан'" :img="'car_preview.png'" :passengers="4"
                    :cars="cars[0]"
                    class="relative before:absolute before:top-0 before:left-0 before:h-[calc(100%+20px)] before:w-0.5 before:bg-[#e5c667] after:absolute after:-bottom-5 after:left-0 after:h-0.5 after:w-full after:bg-[#e5c667]" />
                <CarCard v-model:isOpen="isOpen" :mark="'минивэн'" :img="'car2.png'" :passengers="7" :cars="cars[1]"
                    class="relative before:absolute before:bottom-0 before:right-0 before:h-[calc(100%+22px)] before:w-0.5 before:bg-[#e5c667]" />
            </div>
        </ContentContainer>
    </div>
</template>
