<template>
  <v-container fluid class="bg-gradient-to-r from-blue-500 via-purple-500 to-pink-500 py-12">
    <v-row justify="center">
      <v-col cols="12" sm="8" md="12">
        <!-- Card untuk konten utama -->
        <v-card class="mx-auto rounded-xl" outlined color="transparent" dark elevation="24">
          <v-card-title class="text-center">
            <div class="text-h2 font-weight-black mb-3">Selamat Datang di Aplikasi</div>
          </v-card-title>
          <v-divider></v-divider>
          <v-card-text class="text-center">
            <div class="text-h5 mb-2">Aplikasi ini dibuat oleh:</div>
            <div class="text-subtitle-2">Npm : 40622100142</div>
            <div class="text-subtitle-2">Nama : Muhamad Daffa Khoerudin</div>
          </v-card-text>
          <v-divider></v-divider>
          <v-card-text class="text-center">
            <div class="text-h4 mb-3">Hello!</div>
            <!-- Tombol untuk memunculkan pesan selamat datang -->
            <v-btn @click="toggleGreeting" color="primary" class="elevation-12 rounded-full">
              Toggle Hello
            </v-btn>
          </v-card-text>
        </v-card>
        <!-- Snackbar untuk pesan selamat datang -->
        <v-snackbar v-model="snackbar" :timeout="3000" color="success" top>
          Hello Selamat Datang, Selamat Mencoba Apps Saya
        </v-snackbar>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref } from 'vue'

// Variabel untuk mengontrol tampilan snackbar
const showGreeting = ref(false)
const snackbar = ref(false)

// Fungsi untuk menampilkan snackbar saat tombol ditekan
const toggleGreeting = () => {
  showGreeting.value = !showGreeting.value
  if (showGreeting.value) {
    snackbar.value = true
  }
}
</script>

<style scoped>
.bg-gradient-to-r {
  background: linear-gradient(to right, #2196F3, #9C27B0, #E91E63);
}
.rounded-xl {
  border-radius: 1.5rem;
}
.text-subtitle-2 {
  font-size: 0.875rem;
}
</style>
