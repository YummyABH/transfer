<script setup>
import ContentContainer from './ContentContainer.vue';
import CarCard from './ui/CarCard.vue';
</script>

<template>
    <div class="w-full py-20">
        <h2
            class="mb-20 pl-104 py-2  pr-18 relative before:-right-1 after:-bottom-1.25 after:absolute after:w-1.5 after:-right-1.5 after:h-3.25 bg-[#e5c667] text-white after:bg-[#e5c667] before:-top-1 box-border before:w-3.25 before:bg-[#e5c667] before:absolute before:h-14 before:-rotate-8 inline-block border-y-5 text-2xl font-semibold border-[#e5c667]">
            Транспорт</h2>
        <ContentContainer>
            <div class="flex flex-col gap-10.5">
                <CarCard :img="'car1.jpg'"
                    class="relative before:absolute before:top-0 before:left-0 before:h-[calc(100%+20px)] before:w-0.5 before:bg-[#e5c667] after:absolute after:-bottom-5 after:left-0 after:h-0.5 after:w-full after:bg-[#e5c667]" />
                <CarCard :img="'car2.jpg'"
                    class="relative before:absolute before:bottom-0 before:right-0 before:h-[calc(100%+22px)] before:w-0.5 before:bg-[#e5c667]" />
            </div>
        </ContentContainer>
    </div>
</template>
