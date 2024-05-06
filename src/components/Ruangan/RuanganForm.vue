<template>
  <div>
    <h1>Entry Data Ruangan</h1>
    <!-- Models Database Start -->
    <v-text-field v-model="ruangan.code" label="Kode Ruangan" variant="outlined"></v-text-field>
    <v-text-field v-model="ruangan.nama" label="Nama Ruangan" variant="outlined"></v-text-field>

    <v-btn @click="alertDosen" variant="outlined" block> Submit </v-btn>
    <!-- Models Database End-->
    <br />
    <br />

    <!-- Tampilkan nilai hanya jika showNilai bernilai true -->
    <p v-if="showNilai">Kode Ruangan : {{ ruangan2.code }}</p>
    <p v-if="showNilai">Nama Ruangan: {{ ruangan2.nama }}</p>
  </div>
</template>

<script lang="ts">
import { Ruangan } from '@/model/Ruangan.ts'

export default {
  data() {
    return {
      count: 0,
      nilai: '',
      ruangan: new Ruangan('4123', 'Informatika'),

      showNilai: false,
      ruangan2: {}
    }
  },

  methods: {
    increment() {
      this.count++
    },
    rubahNilai() {
      this.nilai = ' Muhamad Daffa Khoerudin'
      setTimeout(() => {
        this.nilai = ''
      }, 1000)
    },
    alertDosen() {
      if (!this.ruangan.code) {
        alert('Field Kode Ruangan harus diisi!')
      } else if (!this.ruangan.nama) {
        alert('Field Nama Ruangan harus diisi!')
      } else {
        alert(`${this.ruangan.nama} berhasil ditambahkan`)
        this.ruangan2 = this.ruangan
        this.showNilai = true
        setTimeout(() => {
          this.ruangan = ''
        }, 1000)
      }
    }
  },

  mounted() {
    console.log(`The initial count is ${this.ruangan}`)
    console.log(`The initial count is ${this.ruangan2}`)
  }
}
</script>
