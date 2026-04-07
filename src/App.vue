<script setup>
import AppFooter from './components/AppFooter.vue'
import AppHeader from './components/AppHeader.vue'
import BasePreview from './components/BasePreview.vue'
import BaseCars from './components/BaseCars.vue'
import BaseVipCars from './components/BaseVipCars.vue'
import BaseTour from './components/BaseTour.vue'
import BaseAccommodation from './components/BaseAccommodation.vue'
</script>

<template>
  <div class="">
    <AppHeader></AppHeader>
    <main>
      <BasePreview />
      <BaseCars />
      <BaseVipCars />
      <BaseTour />
      <BaseAccommodation />
    </main>
    <AppFooter />
  </div>
</template>

<style>
@import './assets/main.css';
</style>
