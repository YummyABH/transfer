<script setup>
import BaseAdvatages from './BaseAdvatages.vue';
import ContentContainer from './ContentContainer.vue'
import CarVipCard from './ui/CarVipCard.vue'

const cars = [
    [
        {
            price: 7000,
            title: 'Гагра',
        },
        {
            price: 8000,
            title: 'Пицунда',
        },
        {
            price: 9000,
            title: 'Гудаута',
        },
        {
            price: 10000,
            title: 'Новый Афон',
        },
        {
            price: 11000,
            title: 'Сухум',
        },
        {
            price: 14000,
            title: 'Очамчира',
        },
        {
            price: 16000,
            title: 'Ткурчал',
        },
        {
            price: 18000,
            title: 'Гал',
        },
    ],
    [
        {
            price: 8000,
            title: 'Гагра',
        },
        {
            price: 9000,
            title: 'Пицунда',
        },
        {
            price: 10000,
            title: 'Гудаута',
        },
        {
            price: 11000,
            title: 'Новый Афон',
        },
        {
            price: 12000,
            title: 'Сухум',
        },
        {
            price: 15000,
            title: 'Очамчира',
        },
        {
            price: 17000,
            title: 'Ткурчал',
        },
        {
            price: 19000,
            title: 'Гал',
        },
    ],
]
</script>

<template>
    <div class="w-full max-lg:py-5 py-20" id="vip-car">
        <h2
            class="mb-20 max-md:pl-20 max-lg:mb-12 max-lg:pl-40 pl-104 py-2 pr-18 relative before:-right-1 after:-bottom-1.25 after:absolute after:w-1.5 after:-right-1.5 after:h-3.25 bg-[#e5c667] text-white after:bg-[#e5c667] before:-top-1 box-border before:w-3.25 before:bg-[#e5c667] before:absolute before:h-14 before:-rotate-8 inline-block border-y-5 text-2xl font-semibold border-[#e5c667]">
            VIP Транспорт
        </h2>
        <ContentContainer>
            <div
                class="text-xl max-md:max-w- max-md:text-base  font-light mb-25 max-w-200 mx-auto relative before:w-20 before:absolute before:h-20 before:-bottom-5 before:-right-5 before:border-b-[#e5c667] before:border-b before:border-r before:border-r-[#e5c667] after:w-20 after:absolute after:h-20 max-md:before:-right-2 max-md:before:-bottom-2 max-md:after:-left-2 max-md:after:-top-2 after:-left-5 after:-top-5 after:border-l-[#e5c667] after:border-l after:border-t-[#e5c667] after:border-t ">
                Lorem,
                ipsum dolor sit amet consectetur adipisicing elit.
                Dolore fuga
                quia
                provident.
                Dolore,
                dolorum accusamus. Iste, sapiente! Quia officia magnam earum accusantium perferendis! Suscipit minus
                consectetur sit velit aut hic? Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsam sint natus
                molestiae est, quibusdam nemo ea ipsum nam deserunt aliquid alias consequatur possimus a, pariatur odio
                sapiente, voluptate velit doloremque!</div>
            <div class="grid grid-rows-2 gap-y-10">
                <CarVipCard :passengers="4" :img="'car1.png'" :cars="cars[0]" />
                <CarVipCard :passengers="7" :img="'vip_car2.png'" :cars="cars[1]" />
            </div>
            <!-- <div class="flex justify-self-center gap-x-16">
                <div class="my-10 gap-x-4 flex items-center">
                    <div class="w-18 p-2 bg-[#4d4d4d] rounded-xl"><img src="/hello.png" alt=""></div>
                    <div class="">Возможность встречи с табличкой</div>
                </div>
                <div class="my-10 gap-x-4 flex items-center">
                    <div class="w-18 p-2 bg-[#4b4b4b] rounded-xl"><img src="/water.png" alt=""></div>
                    <div class="">В авто есть вода</div>
                </div>
            </div> -->
            <BaseAdvatages />
        </ContentContainer>
    </div>
</template>
