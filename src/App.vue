<script setup>
import AppFooter from './components/AppFooter.vue'
import AppHeader from './components/AppHeader.vue'
import BasePreview from './components/BasePreview.vue'
import BaseCars from './components/BaseCars.vue'
</script>

<template>
  <div class="">
    <AppHeader></AppHeader>
    <main>
      <BasePreview />
      <BaseCars />
    </main>
    <AppFooter />
  </div>
</template>

<style>
@import './assets/main.css';
</style>
