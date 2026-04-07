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
    <div class="w-full max-w-4xl mx-auto p-6 pb-0 ">
        <!-- Горизонтальный список заголовков -->
        <div class="flex gap-2 pb-4 mb-6 scrollbar-thin scrollbar-thumb-gray-300 scrollbar-track-gray-100">
            <button v-for="(item, index) in tabs" :key="index" @click="activeTab = index"
                class="px-6 py-3 cursor-pointer text-base font-medium rounded-full transition-all duration-300 whitespace-nowrap"
                :class="[
                    activeTab === index
                        ? 'bg-[#e5c667] text-white shadow-lg shadow-blue-200 scale-105'
                        : 'bg-gray-100 text-gray-600 hover:bg-gray-200 hover:text-gray-800'
                ]">
                {{ item.title }}
            </button>
        </div>

        <!-- Отображаемый текст под списком -->
        <div class="bg-white rounded-xl shadow-lg p-6 min-h-50 animate-fadeIn">
            <p class="text-gray-700 leading-relaxed">
                {{ tabs[activeTab]?.content }}
            </p>
        </div>
    </div>
</template>


<style scoped>
@keyframes fadeIn {
    from {
        opacity: 0;
        transform: translateY(10px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.animate-fadeIn {
    animation: fadeIn 0.3s ease-out;
}

/* Стили для скроллбара (опционально) */
.scrollbar-thin::-webkit-scrollbar {
    height: 6px;
}

.scrollbar-thin::-webkit-scrollbar-track {
    background: #f1f1f1;
    border-radius: 10px;
}

.scrollbar-thin::-webkit-scrollbar-thumb {
    background: #cbd5e1;
    border-radius: 10px;
}

.scrollbar-thin::-webkit-scrollbar-thumb:hover {
    background: #94a3b8;
}
</style>