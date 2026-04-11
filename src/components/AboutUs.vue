<script setup>
const isOpen = defineModel('isOpen')
</script>

<template>
    <section class="py-10 px-4 bg-white">
        <div class="max-w-4xl mx-auto">
            <!-- Заголовок -->
            <h2 class="text-3xl md:text-4xl font-bold text-center text-gray-900 mb-4">
                О компании
            </h2>
            <div class="w-20 h-1 bg-amber-500 mx-auto mb-10 rounded-full"></div>

            <!-- Весь текст одним блоком -->
            <div class="space-y-4 text-gray-700 leading-relaxed text-base md:text-lg">
                <p>
                    <span class="font-semibold text-gray-900">Здравствуйте, друзья!</span><br />
                    Меня зовут Алиас, я основатель компании и уже более
                    <span class="font-semibold">10 лет</span> создаю для путешественников
                    незабываемые впечатления от Абхазии.
                </p>

                <p>
                    Отдельное внимание я уделяю <span class="font-semibold text-gray-900">трансферу</span> —
                    ведь именно с него начинается ваш отдых. Никаких очередей на границе, поисков попуток
                    или переживаний «как доехать».
                </p>

                <p class="font-semibold text-gray-900 pt-2">Вы получаете:</p>
                <ul class="space-y-2 pl-4">
                    <li>· личного водителя, который встретит вас прямо у выхода из российского паспортного контроля;
                    </li>
                    <li>· комфортабельный автомобиль (с кондиционером, зарядкой для телефона и водой);</li>
                    <li>· помощь в прохождении границы — я подскажу все нюансы, чтобы вы пересекли её быстро и без
                        нервов;</li>
                    <li>· трансфер «от двери до двери»: из аэропорта Адлера, ж/д вокзала или из любого места в Сочи
                        прямо до вашего отеля или гостевого дома в Абхазии.</li>
                </ul>

                <p>
                    Я лично отвечаю за безопасность, пунктуальность и комфорт в каждой детали.
                    Покажу вам удивительные места, стану проводником в мир культуры и традиций моей родины.
                    Верю, что каждый гость заслуживает лучшего — и обеспечиваю это в каждой поездке.
                </p>

                <p>
                    Исследуйте древние места, насладитесь пейзажами, погрузитесь в обычаи гостеприимной Абхазии
                    — и главное, проведите отдых без единой дорожной проблемы.
                </p>

                <p class="font-semibold text-center pt-4">
                    Свяжитесь со мной сегодня — и я организую не только трансфер, но и всё путешествие вашей мечты в
                    Абхазию.
                </p>

                <!-- Кнопка -->
                <div class="text-center pt-4">
                    <button @click="isOpen = !isOpen"
                        class="w-max px-2 mx-auto cursor-pointer bg-[#ddb642] hover:bg-[#e5c667] active:bg-[#baa35e] transition-colors text-white font-semibold py-4 rounded-2xl text-base shadow-sm flex items-center justify-center gap-2">
                        Связаться со мной
                    </button>
                </div>
            </div>
        </div>
    </section>
</template>