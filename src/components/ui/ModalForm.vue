<script setup>
import { ref } from 'vue'

const BOT_TOKEN = '8466039071:AAE4taHblZr0Ow2lxqzyk775FukYX8aYfg0'
const CHAT_ID = 584472256

const isOpen = defineModel('isOpen')
const isSubmitting = ref(false)

const form = ref({
    fullName: '',
    phone: ''
})

function closeModal() {
    isOpen.value = false
    document.body.style.overflow = 'visible'
}

function formatPhone(e) {
    let value = e.target.value.replace(/\D/g, '')

    if (value.length > 10) value = value.slice(0, 10)

    let formatted = ''
    if (value.length > 0) formatted += '(' + value.slice(0, 3)
    if (value.length > 3) formatted += ') ' + value.slice(3, 6)
    if (value.length > 6) formatted += '-' + value.slice(6, 8)
    if (value.length > 8) formatted += '-' + value.slice(8, 10)

    form.value.phone = formatted
}

// Экранирование специальных символов для MarkdownV2
function escapeMarkdownV2(text) {
    if (!text) return ''
    return String(text).replace(/([_*[\]()~`>#+\-=|{}.!])/g, '\\$1')
}

async function submitForm() {
    if (!form.value.fullName || !form.value.phone || isSubmitting.value) return

    isSubmitting.value = true

    const messageText = `
📨 *Новая заявка с сайта*

👤 *ФИО:* ${escapeMarkdownV2(form.value.fullName)}
📞 *Телефон:* 7${escapeMarkdownV2(form.value.phone)}

🕒 ${new Date().toLocaleString('ru-RU')}
  `.trim()

    try {
        const response = await fetch(`https://api.telegram.org/bot${BOT_TOKEN}/sendMessage`, {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json',
            },
            body: JSON.stringify({
                chat_id: CHAT_ID,
                text: messageText,
                parse_mode: 'HTML'
            })
        })

        const data = await response.json()

        if (data.ok) {
            alert('✅ Заявка успешно отправлена!\nМы свяжемся с вами в ближайшее время.')

            // Очистка формы
            form.value.fullName = ''
            form.value.phone = ''
            closeModal()
        } else {
            throw new Error(data.description || 'Ошибка отправки')
        }

    } catch (error) {
        console.error('Ошибка отправки в Telegram:', error)
        alert('❌ Не удалось отправить заявку. Попробуйте ещё раз или позвоните нам напрямую.')
    } finally {
        isSubmitting.value = false
    }
}

// Закрытие по клавише ESC
document.addEventListener('keydown', (e) => {
    if (e.key === 'Escape' && isOpen.value) {
        closeModal()
    }
})
</script>

<template>
    <div>
        <Transition name="fade">
            <div v-if="isOpen" class="fixed inset-0 z-50 flex items-center justify-center p-4">
                <!-- Притемнение фона -->
                <div class="absolute inset-0 bg-black/70 transition-opacity" @click="closeModal" />

                <!-- Само модальное окно -->
                <div class="relative bg-white rounded-2xl shadow-2xl w-full max-w-md overflow-hidden" @click.stop>
                    <!-- Шапка -->
                    <div class="px-6 pt-6 pb-4 border-b border-gray-100">
                        <h2 class="text-2xl font-semibold text-gray-900">
                            Введите ваши данные
                        </h2>
                        <p class="text-gray-500 text-sm mt-1">
                            Мы свяжемся с вами в ближайшее время
                        </p>
                    </div>

                    <!-- Форма -->
                    <form @submit.prevent="submitForm" class="p-6 space-y-5">
                        <!-- ФИО -->
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-1.5">
                                Фамилия, имя и отчество
                            </label>
                            <input v-model="form.fullName" type="text" placeholder="КАК К ВАМ ОБРАЩАТЬСЯ ?" required
                                class="w-full px-4 py-3 border border-gray-300 rounded-xl focus:outline-none focus:border-[#e5c667] focus:ring-2 focus:ring-[#e5c667]/30 transition-all" />
                        </div>

                        <!-- Номер телефона -->
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-1.5">
                                Номер телефона
                            </label>
                            <div class="relative">
                                <div class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-500 font-medium">
                                    +7
                                </div>
                                <input v-model="form.phone" type="tel" placeholder="(999) 123-45-67" required
                                    maxlength="15" @input="formatPhone"
                                    class="w-full pl-12 pr-4 py-3 border border-gray-300 rounded-xl focus:outline-none focus:border-[#e5c667] focus:ring-2 focus:ring-[#e5c667]/30 transition-all" />
                            </div>
                        </div>

                        <!-- Кнопка отправки -->
                        <button type="submit" :disabled="isSubmitting"
                            class="cursor-pointer text-white w-full py-4 bg-[#e5c667] hover:bg-[#d4b55a] active:bg-[#c9a94f] font-semibold text-lg rounded-2xl transition-all disabled:opacity-70 disabled:cursor-not-allowed mt-4">
                            {{ isSubmitting ? 'Отправляем...' : 'Отправить заявку' }}
                        </button>
                    </form>

                    <!-- Крестик для закрытия -->
                    <button @click="closeModal"
                        class="cursor-pointer absolute top-5 right-5 w-8 h-8 flex items-center justify-center text-gray-400 hover:text-gray-600 transition-colors">
                        ✕
                    </button>
                </div>
            </div>
        </Transition>
    </div>
</template>

<style scoped>
.fade-enter-active,
.fade-leave-active {
    transition: opacity 200ms ease;
}

.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}

.fade-enter-from .relative,
.fade-leave-to .relative {
    transform: scale(0.95);
    transition: transform 200ms ease;
}
</style>