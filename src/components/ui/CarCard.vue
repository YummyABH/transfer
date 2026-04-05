<script setup>
import IconPerson from '@/components/icons/IconPerson.vue';
defineProps({
    img: String
})
</script>

<template>
    <div class="shadow-2xl flex">
        <div class="w-130 border-r-3 border-[#000000]">
            <img class="" :src="`/public/${img}`" alt="">
        </div>
        <div class="flex flex-col flex-1">
            <h3 class="px-4 py-2 text-xl font-medium">Автомобиль седан до 4-х мест</h3>
            <div class="inline-block text-base  px-4 py-4 flex-1  ">Забираем от Аэропорта Сочи,
                железнодорожный
                вокзал Адлер, либо по указанному адресу!
                Трансфер на комфортном автомобиле седан - посадка до 4-х мест.</div>
            <select class="w-max! bg-zinc-600! py-1! text-white! px-4!">
                <option>Цандрипш</option>
                <option>Холодная речка</option>
                <option>Гагра</option>
                <option>Алахадзы</option>
                <option>Пицунда</option>
                <option>Лидзава</option>
                <option>Монашеское ущелье</option>
                <option>Мюсера</option>
                <option>Гудаута</option>
                <option>Новый Афон</option>
                <option>Агудзера</option>
                <option>Дранда</option>
                <option>Кындги</option>
                <option>Тамыш</option>
                <option>Очамчира</option>
                <option>Ткварчал</option>
                <option>Гал</option>
            </select>
            <div class="flex items-center border-t bg-[#000000] px-4 py-4">
                <div class="flex justify-between w-full">
                    <div class="flex items-center">
                        <div class="flex gap-x-1 pr-4 border-r border-r-[#e5c667] text-white">
                            <span class="text-xl font-">Цена:</span>
                            <span class="text-xl font-bold">3500</span>
                        </div>
                        <div class="flex gap-x-2 pl-4">
                            <IconPerson />
                            <span class="text-xl text-white font-semibold">4</span>
                        </div>
                    </div>
                    <div
                        class=" box-border border-3 px-6 py-2 text-white ml-10 border-white  hover:border-[#ffde7ba4]  hover:bg-[#ffde7ba4] duration-200 cursor-pointer">
                        <span>
                            Заказать
                        </span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>