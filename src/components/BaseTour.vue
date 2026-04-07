<script setup>
import ContentContainer from './ContentContainer.vue';
import TourCard from './ui/TourCard.vue';

const tourInfo = [
    {
        price: '15 000',
        advantages: [
            'Ткуарчал', 'Водопады: Ирина, Великан, Святой', 'Поселки Акармара и Джантуха', 'Обед с видом на водопад Золотоносец'
        ],
    },
    {
        price: '8 000',
        advantages: [
            'Новоафонская пещера', 'Пещера Симона Кананита', 'Нофоафонский монастырь', 'Анакопийская крепость'
        ],
    },
    {
        price: '15 000',
        advantages: [
            'Юпшарский каньон', 'Голубое Озеро', 'Чабгарский карниз', 'Рица (набережная, смотровая)'
        ],
    },
    {
        price: '10 000',
        advantages: [
            'Черниговка', 'Дранда (собор 6 века)', 'Киндги(горячий источник)', 'Ольгинский водопад'
        ]
    },
]
</script>

<template>
    <div class="w-full py-20" id="tour">
        <h2
            class="mb-20 pl-104 py-2 pr-18 relative before:-right-1 after:-bottom-1.25 after:absolute after:w-1.5 after:-right-1.5 after:h-3.25 bg-[#e5c667] text-white after:bg-[#e5c667] before:-top-1 box-border before:w-3.25 before:bg-[#e5c667] before:absolute before:h-14 before:-rotate-8 inline-block border-y-5 text-2xl font-semibold border-[#e5c667]">
            Индивидуальные и семейные туры по Абхазии
        </h2>
        <ContentContainer>
            <div
                class="text-xl font-light mb-25  relative before:w-20 before:absolute before:h-20 before:-bottom-5 before:-right-5 before:border-b-[#e5c667] before:border-b before:border-r before:border-r-[#e5c667] after:w-20 after:absolute after:h-20 after:-left-5 after:-top-5 after:border-l-[#e5c667] after:border-l after:border-t-[#e5c667] after:border-t ">
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
            <div class="grid grid-cols-1 sm:grid-cols-2 grid-rows-2 gap-1">
                <TourCard :list="tourInfo[0]" :title="'Город герой  — Ткуарчал'" :img="'tour1.jpg'" />
                <TourCard :list="tourInfo[1]" :title="'Новый Афон'" :img="'tour2.jpg'" />
                <TourCard :list="tourInfo[2]" :title="'Озеро Рица  — жемчужина Кавказа'" :img="'tour3.webp'" />
                <TourCard :list="tourInfo[3]" :title="'Черниговка'" :img="'tour4.jpg'" />
            </div>
            <h3 class="text-2xl my-10 text-center font-semibold">Удобства</h3>
            <div class="mt-10 grid grid-cols-2 gap-4 grid-rows-2 ">
                <div class="flex col-span-1">
                    <div class="w-24 p-2 rounded-l-xl bg-[#feebab]"><img class="" src="/car.png" alt=""></div>
                    <span class="pl-4 flex items-center rounded-r-xl text-white bg-[#e4b938]">Автомобиль современный,
                        чистый,
                        ухоженный.
                        Безопасный
                        транспорт это
                        залог
                        комфортной поездки.
                    </span>
                </div>
                <div class="flex col-span-1  w-full">
                    <div class="w-18 aspect-square justify-center flex items-center  p-2 rounded-l-xl bg-[#feebab]">
                        <img class="max-w-full h-10 max-h-full object-cover" src="/sun.png" alt="">
                    </div>
                    <span class="pl-4 w-full flex items-center rounded-r-xl text-white bg-[#e4b938]">Кондиционер в
                        машине:
                        летом свежо, зимой тепло.
                    </span>
                </div>
                <div class="flex col-span-1  w-full">
                    <div class=" justify-center flex items-center aspect-square p-2 rounded-l-xl bg-[#feebab]"><img
                            class="max-w-full h-10 max-h-full object-cover" src="/wifi.png" alt=""></div>
                    <span class="pl-4 w-full flex items-center rounded-r-xl text-white bg-[#e4b938]">
                        Зарядка гаджетов, бесплатный Wi-Fi
                    </span>
                </div>
                <div class="flex col-span-1  w-full">
                    <div class=" justify-center flex items-center aspect-square p-2 rounded-l-xl bg-[#feebab]"><img
                            class="max-w-full h-10 max-h-full object-cover" src="/chair.png" alt=""></div>
                    <span class="pl-4 w-full flex items-center rounded-r-xl text-white bg-[#e4b938]">
                        Детское кресло.
                    </span>
                </div>
                <div class="flex col-span-1  w-full">
                    <div class=" justify-center flex items-center aspect-square p-2 rounded-l-xl bg-[#feebab]"><img
                            class="max-w-full h-10 max-h-full object-cover" src="/map.png" alt=""></div>
                    <span class="pl-4 pr-2 w-full flex items-center rounded-r-xl text-white bg-[#e4b938]">
                        Пунктуальность.
                        Мы за то, чтобы не торопиться в дороге, а выезжать вовремя. По этому Ваш водитель будет ожидать
                        Вас за 10-15 минут до поездки.
                    </span>
                </div>
            </div>
        </ContentContainer>
    </div>
</template>