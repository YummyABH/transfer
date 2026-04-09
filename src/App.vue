<script setup>
import AppFooter from './components/AppFooter.vue'
import AppHeader from './components/AppHeader.vue'
import BasePreview from './components/BasePreview.vue'
import BaseCars from './components/BaseCars.vue'
import BaseVipCars from './components/BaseVipCars.vue'
import BaseTour from './components/BaseTour.vue'
import ContentContainer from './components/ContentContainer.vue'

// import BaseReview from './components/BaseReview.vue'

</script>

<template>
  <div class="">
    <AppHeader></AppHeader>
    <main>
      <BasePreview />
      <BaseCars />
      <BaseVipCars />
      <BaseTour />
      <!-- <ContentContainer>
        <div style="width:560px;height:800px;overflow:hidden;position:relative;"><iframe
            style="width:100%;height:100%;border:1px solid #e6e6e6;border-radius:8px;box-sizing:border-box"
            src="https://yandex.ru/maps-reviews-widget/134107937903?comments"></iframe><a
            href="https://yandex.ru/maps/org/delfin/134107937903/" target="_blank"
            style="box-sizing:border-box;text-decoration:none;color:#b3b3b3;font-size:10px;font-family:YS Text,sans-serif;padding:0 20px;position:absolute;bottom:8px;width:100%;text-align:center;left:0;overflow:hidden;text-overflow:ellipsis;display:block;max-height:14px;white-space:nowrap;padding:0 16px;box-sizing:border-box">Дельфин
            на карте Гулрыпшского района — Яндекс Карты</a></div>
      </ContentContainer> -->
      <!--<BaseAccommodation /> -->
      <!-- <BaseReview /> -->
    </main>
    <AppFooter />
  </div>
</template>

<style>
@import './assets/main.css';
</style>
