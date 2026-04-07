<script setup>
import { onMounted, onUnmounted, ref } from 'vue';
import ContentContainer from './ContentContainer.vue';
import IconLogo from './icons/IconLogo.vue';
import IconTelegramm from './icons/IconTelegramm.vue';
import IconWhatsapp from './icons/IconWhatsapp.vue';

const isScrolled = ref(false)

const handleScroll = () => {
    isScrolled.value = window.scrollY > 0
}

onMounted(() => {
    window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
    window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
    <header :class="[
        'fixed backdrop-blur-md top-0 left-1/2 transform -translate-x-1/2 max-w-screen w-full z-2 text-white py-4 transition-all duration-300',
        isScrolled ? 'bg-[#1b1b1b] border-b border-[#ffde7b3b]' : 'bg-white/1 border-b border-[#ffde7b3b]'
    ]">
        <ContentContainer>
            <div class="flex justify-between items-center">
                <div class="flex items-center">
                    <IconLogo class="w-14 mr-20" />
                    <ul class="flex gap-x-0">
                        <a href="#transfer">
                            <li class="text-base font-light nav-item">Трансфер</li>
                        </a>
                        <a href="#car">
                            <li class="text-base font-light nav-item">Транспорт</li>
                        </a>
                        <a href="#vip-car">
                            <li class="text-base font-light nav-item">VIP Транспорт</li>
                        </a>
                        <a href="#tour">
                            <li class="text-base font-light nav-item">Туры</li>
                        </a>
                        <a href="#accommodation">
                            <li class="text-base font-light nav-item">Размещение</li>
                        </a>
                    </ul>
                </div>
                <div class="flex gap-x-10 items-center">
                    <div class="flex gap-x-4">
                        <div class="bg-[#0084c6] duration-200 cursor-pointer rounded-lg flex p-2 
                            transition-all 
                            hover:bg-[#006a9e]
                            hover:shadow-[inset_0_4px_10px_rgba(0,0,0,0.35)]
                            active:scale-95 
                            active:shadow-[inset_0_8px_16px_rgba(0,0,0,0.5)]">
                            <IconTelegramm />
                        </div>
                        <div class="bg-[#01e675] duration-200 cursor-pointer rounded-lg flex p-2 
                            transition-all 
                            hover:bg-[#70d850]
                            hover:shadow-[inset_0_4px_10px_rgba(0,0,0,0.35)]
                            active:scale-95 
                            active:shadow-[inset_0_8px_16px_rgba(0,0,0,0.5)]">
                            <IconWhatsapp />
                        </div>
                    </div>
                    <div
                        class="px-4 py-3 border border-[#ffdf7b] hover:border-[#ffde7ba4] hover:bg-[#ffde7ba4] duration-200 cursor-pointer">
                        Оставить заявку</div>
                </div>
            </div>
        </ContentContainer>
    </header>
</template>

<style scoped>
.nav-item {
    position: relative;
    padding: 8px 0;
    color: inherit;
    text-decoration: none;
    font-weight: 300;
    transition: color 0.3s ease;
    cursor: pointer;
}

/* Анимация обводки + заливка цвета */
.nav-item::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 0;
    height: 2px;
    background: #ffdf7b;
    transition: width 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}

/* При наведении: сначала рисуется линия, потом меняется цвет текста */
.nav-item:hover {
    color: #ffdf7b;
}

.nav-item:hover::after {
    width: 100%;
}

/* Дополнительно: можно сделать более эффектную обводку по всему контуру */

.nav-item {
    position: relative;
    padding: 8px 16px;
    border-radius: 4px;
    transition: all 0.4s ease;
}

/* Вариант 2 — обводка по всему элементу (рамка) */
.nav-item::before {
    content: '';
    position: absolute;
    inset: 0;
    border: 2px solid transparent;
    transition: all 0.5s ease;
    opacity: 0;
}

.nav-item:hover::before {
    border-color: #ffdf7b;
    opacity: 1;
}

.nav-item:hover {
    color: #ffdf7b;
    background: rgba(255, 223, 123, 0.08);
    /* лёгкий фон при наведении */
}
</style>