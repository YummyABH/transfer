<script setup>
import AppFooter from './components/AppFooter.vue'
import AppHeader from './components/AppHeader.vue'
import BasePreview from './components/BasePreview.vue'
import BaseHousing from './components/BaseHousing.vue'
import AboutUs from './components/AboutUs.vue'
import BaseCars from './components/BaseCars.vue'
import BaseVipCars from './components/BaseVipCars.vue'
import BaseTour from './components/BaseTour.vue'
import ContentContainer from './components/ContentContainer.vue'
import ModalForm from './components/ui/ModalForm.vue'
import IconWhatsapp from './components/icons/IconWhatsapp.vue'
import IconTelegramm from './components/icons/IconTelegramm.vue'
import { ref } from 'vue'

// import BaseReview from './components/BaseReview.vue'
const isOpen = ref(false)
</script>

<template>
  <ModalForm v-model:isOpen="isOpen" />
  <div class="">
    <AppHeader v-model:isOpen="isOpen"></AppHeader>
    <main>
      <BasePreview v-model:isOpen="isOpen" />
      <BaseCars v-model:isOpen="isOpen" />
      <BaseVipCars v-model:isOpen="isOpen" />
      <BaseTour v-model:isOpen="isOpen" />
      <!-- <BaseAccommodation v-model:isOpen="isOpen" /> -->
      <BaseHousing v-model:isOpen="isOpen" />
      <ContentContainer>
        <div class="flex gap-x-16 ">
          <div class="w-full flex max-sm:flex-col max-sm:gap-8 max-w-140 mx-auto mb-20">
            <div class="relative w-full overflow-hidden rounded-2xl border border-gray-200 shadow-sm bg-white">

              <div class="relative pt-[142.86%]">
                <iframe class="absolute inset-0 w-full h-full border-0"
                  src="https://yandex.ru/maps-reviews-widget/134107937903?comments" allowfullscreen
                  loading="lazy"></iframe>
              </div>

              <a href="https://yandex.ru/maps/org/delfin/134107937903/" target="_blank"
                class="block px-4 py-3 text-center text-xs text-gray-400 hover:text-gray-500 transition-colors font-medium">
                Дельфин на карте Гулрыпшского района — Яндекс Карты
              </a>
            </div>
            <div class="">
              <div class="mb-10 text-start ml-10 max-sm:mx-auto flex flex-col gap-4">
                <h2 class="text-2xl font-semibold mb-2">Контакты</h2>
                <div class="flex flex-col gap-2">
                  <span class="text-xl">
                    Телефон
                  </span>
                  <span class="inline-block min-w-max">+7 (940) 962-62-90</span>
                </div>
                <div class="flex flex-col gap-y-2">
                  <span class="text-xl mb-4">
                    Соц. сети
                  </span>
                  <span class=" min-w-max flex gap-4">
                    <a href="https://wa.me/message/5VZS6ZUKG5SSE1" target="_blank">
                      <div class="bg-[#01e675] w-max duration-200 cursor-pointer rounded-lg flex p-2 
                              transition-all 
                              hover:bg-[#70d850]
                              hover:shadow-[inset_0_4px_10px_rgba(0,0,0,0.35)]
                              active:scale-95 
                              active:shadow-[inset_0_8px_16px_rgba(0,0,0,0.5)]">
                        <IconWhatsapp />
                      </div>
                    </a>
                    <a href="tg:@gostevoi_dom_delfine989" target="_blank">
                      <div class="bg-[#0084c6] w-max duration-200 cursor-pointer rounded-lg flex p-2 
                              transition-all 
                              hover:bg-[#006a9e]
                              hover:shadow-[inset_0_4px_10px_rgba(0,0,0,0.35)]
                              active:scale-95 
                              active:shadow-[inset_0_8px_16px_rgba(0,0,0,0.5)]">
                        <IconTelegramm />
                      </div>
                    </a>
                    <a href="https://max.ru/u/f9LHodD0cOJWv4FpXUT5fnw0AlV0XkGw8P7eq1lEXDadg6m1PJNAu9eTCxU"
                      target="_blank">
                      <img class="w-10 h-10" src="/max.png" alt="">
                    </a>
                  </span>
                </div>
              </div>
              <div class="text-start ml-10 max-sm:mx-auto flex flex-col gap-4">
                <h2 class="text-2xl font-semibold mb-2">Лицензия</h2>
                <a href="/certificate.png" download class="flex gap-x-2 items-center">
                  <img class="w-10 " src="/icon_sert.png" alt="">
                  <span class="hover:text-[#616161] duration-200 text-base inline-block w-max">
                    Скачать сертификат
                  </span>
                </a>
              </div>
            </div>
          </div>
        </div>
      </ContentContainer>
      <AboutUs v-model:isOpen="isOpen" />
      <!-- <BaseReview /> -->
    </main>
    <AppFooter v-model:isOpen="isOpen" />
  </div>
</template>

<style>
@import './assets/main.css';
</style>
