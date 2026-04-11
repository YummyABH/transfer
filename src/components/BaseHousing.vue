<script setup>
import ContentContainer from './ContentContainer.vue'
import HotelCard from './ui/HotelCard.vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/css'
import 'swiper/css/pagination'
import 'swiper/css/autoplay'
import 'swiper/css/autoplay'
import { Autoplay } from 'swiper/modules'

const isOpen = defineModel('isOpen')
const modules = [Autoplay]

const hotelInfo = [
    {
        price: '3 000',
        advantages: [
            'Прямо на берегу моря (30 шагов до воды)', 'Собственный песчаный пляж - чистый и пустой', '3 формата размещения со всеми удобствами под любой бюджет.', 'Каждый номер оборудован кондиционером и Wi-Fi.', 'В шаговой доступности супермаркет, пекарня, кафе и рестораны, аптека', 'И еще многое для вашей радости: барбекю на пляже, пляжный волейбол, домашние напитки и деликатесы, фруктовый сад и т.д.'
        ],
        slidesImg: [
            'tour4.jpg', 'tour1.jpg', 'tour2.jpg',
        ]
    },
    {
        price: '8 000',
        advantages: [
            'Приглашаем вас на отдых в Абхазию. Гостевой дом "Аллея роз" находится в 7 км от центра г.Сухума в тихом, спокойном посёлке Каштак, в 3-х мин. ходьбы от пляжа на берегу Чёрного моря.', 'К услугам гостей кухня, зона барбекю с мангалом и беседкой. На территории- аккуратный сад, аллея роз, просторная терраса, бесплатный Wi-Fi доступен на всей территории. В номерах есть кондиционер, телевизор, санузел. Рядом кафе, магазины, остановка общественного транспорта.'],
        slidesImg: [
            'tour4.jpg', 'tour1.jpg', 'tour2.jpg',
        ]
    }
]
</script>

<template>
    <div class="w-full ">

        <div class="w-full pb-15 pt-0" id="accommodation">
            <h2
                class=" max-sm:text-sm max-sm:before:h-0 max-sm:after:h-0 max-sm:after:w-0 max-sm:before:w-0  max-md:pl-20 max-lg:mb-12 max-lg:pl-40 pl-104 py-2 pr-18 relative before:-right-1 after:-bottom-1.25 after:absolute after:w-1.5 after:-right-1.5 after:h-3.25 bg-[#e5c667] text-white after:bg-[#e5c667] before:-top-1 box-border before:w-3.25 before:bg-[#e5c667] before:absolute before:h-14 before:-rotate-8 inline-block border-y-5 text-2xl font-semibold border-[#e5c667]">
                Размещение в Абхазии
            </h2>
        </div>
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
            <div class="mb-20 flex gap-4 ">

                <HotelCard v-model:isOpen="isOpen" class="h-full flex-1" :list="hotelInfo[0]" />
                <!-- <HotelCard v-model:isOpen="isOpen" class="h-full flex-1" :list="hotelInfo[1]" />
                    <HotelCard v-model:isOpen="isOpen" class="h-full flex-1" :list="hotelInfo[0]" />
                    <HotelCard v-model:isOpen="isOpen" class="h-full flex-1" :list="hotelInfo[0]" />
                    <HotelCard v-model:isOpen="isOpen" class="h-full flex-1" :list="hotelInfo[0]" /> -->
            </div>
        </ContentContainer>
    </div>
</template>