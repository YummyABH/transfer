        <script setup>
        import { ref } from 'vue'

        // Определение структуры данных
        const tabs = ref([
            {
                title: 'Преимущества',
                content: 'В этом разделе перечислены ключевые преимущества. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
            },
            {
                title: 'Особенности',
                content: 'Здесь описаны уникальные особенности и характеристики. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.'
            },
            {
                title: 'Контакты',
                content: 'Контактная информация для связи с нами. Вы можете связаться по электронной почте или по телефону. Мы всегда рады ответить на ваши вопросы!'
            }
        ])

        // Активная вкладка (по умолчанию 0 - первая)
        const activeTab = ref(0)
</script>
        
<template>
    <div class="w-full mt-10 max-w-4xl mx-auto px-4 md:px-6 pb-8">

        <!-- Горизонтальный список табов с прокруткой -->
        <div
            class="flex gap-2 pb-6 overflow-x-auto scrollbar-thin scrollbar-thumb-gray-300 scrollbar-track-transparent snap-x snap-mandatory -mx-1 px-1">
            <button v-for="(item, index) in tabs" :key="index" @click="activeTab = index"
                class="flex-shrink-0 px-6 py-3.5 text-sm md:text-base font-medium rounded-2xl transition-all duration-300 whitespace-nowrap snap-start"
                :class="[
                    activeTab === index
                        ? 'bg-[#e5c667] text-white shadow-lg shadow-[#e5c667]/30 scale-[1.03]'
                        : 'bg-gray-100 hover:bg-gray-200 text-gray-600 hover:text-gray-800'
                ]">
                {{ item.title }}
            </button>
        </div>

        <!-- Контент таба -->
        <div class="bg-white rounded-2xl shadow-xl p-6 md:p-8 min-h-[180px] transition-all duration-300">
            <p class="text-gray-700 leading-relaxed text-[15px] md:text-base">
                {{ tabs[activeTab]?.content }}
            </p>
        </div>
    </div>
</template>


<style scoped>
/* Плавная анимация появления контента */
@keyframes fadeIn {
    from {
        opacity: 0;
        transform: translateY(12px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.animate-fadeIn {
    animation: fadeIn 0.4s ease-out forwards;
}

/* Кастомный скроллбар для табов (тонкий и красивый) */
.scrollbar-thin::-webkit-scrollbar {
    height: 7px;
}

.scrollbar-thin::-webkit-scrollbar-track {
    background: transparent;
    border-radius: 10px;
}

.scrollbar-thin::-webkit-scrollbar-thumb {
    background: #cbd5e1;
    border-radius: 10px;
}

.scrollbar-thin::-webkit-scrollbar-thumb:hover {
    background: #94a3b8;
}

/* Скрываем стрелки прокрутки в Firefox */
.scrollbar-thin {
    scrollbar-width: thin;
    scrollbar-color: #cbd5e1 transparent;
}
</style>