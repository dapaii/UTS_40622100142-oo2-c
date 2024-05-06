<template>
  <v-container>
    <v-col cols="12" sm="12" md="12">
      <v-card border="opacity-10 sm" class="mx-auto" width="500" height="500" rounded="xl" variant="text">
        <template v-slot:title>
          <div class="text-h4 mt-5 mr-5 ml-5 text-center">Entry Data Dosen</div>
        </template>

        <template v-slot:text>
          <div class="mt-3 mb-2 mr-5 ml-5">
            <!-- Models Database Start -->
            <v-text-field v-model="dosen.nidn" label="NIDN" variant="outlined"></v-text-field>
            <v-text-field v-model="dosen.nama" label="Nama" variant="outlined"></v-text-field>
            <v-btn @click="alertDosen" variant="outlined" block> Submit </v-btn>
            
            <div class="mt-5">
              <p v-if="showNilai">nidn: {{ dosen2.nidn }}</p>
              <p v-if="showNilai">Nama: {{ dosen2.nama }}</p>
            </div>
            <!-- Tampilkan nilai hanya jika showNilai bernilai true -->
          </div>
        </template>
        
      </v-card>
    </v-col>
  </v-container>
</template>

<script lang="ts">
import { Dosen } from '@/model/Dosen.ts'

export default {
  data() {
    return {
      count: 0,
      nilai: '',
      dosen: new Dosen('1234', 'bambang', 3.4),

      showNilai: false,
      dosen2: {}
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
      if (!this.dosen.nidn) {
        alert('Field NIDN harus diisi!')
      } else if (this.dosen.nama === '') {
        alert('Field Nama harus diisi!')
      } else {
        alert(`${this.dosen.nama} berhasil ditambahkan`)
        this.dosen2 = this.dosen
        this.showNilai = true
        setTimeout(() => {
          this.dosen = ''
        }, 1000)
      }
    }
  },

  mounted() {
    console.log(`The initial count is ${this.dosen}`)
    console.log(`The initial count is ${this.dosen2}`)
  }
}
</script>


