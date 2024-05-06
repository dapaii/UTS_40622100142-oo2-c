<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import LeftNav from '@/components/navbar/LeftNav.vue'
</script>

<template>
  <v-layout class="rounded rounded-md">
    <v-app-bar
      title="Aplikasi Penjadwalan Kuliah"
      image="https://cdn.vuetifyjs.com/images/backgrounds/bg-2.jpg"
      theme="dark"
      permanent
      expand-on-hover
      rail
    ></v-app-bar>

    <LeftNav />

    <v-main class="d-flex align-center justify-center" style="min-height: 300px">
      <RouterView />
    </v-main>
  </v-layout>
</template>

<style>
.v-layout {
  display: block !important;
}
</style>
