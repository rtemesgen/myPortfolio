<template>
  <div class="app-shell">
    <SiteHeader />
    <router-view />
  </div>
</template>

<script setup>
import SiteHeader from './components/SiteHeader.vue'
</script>
