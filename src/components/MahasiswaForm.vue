<template>
  <v-container>
    <div class="outer-box">
      <h2>Entry Data Mahasiswa</h2>
      <v-row>
        <v-text-field label="NPM" variant="outlined"></v-text-field>
      </v-row>
      <v-row>
        <v-text-field label="Nama" v-model="mhs.nama" variant="outlined"></v-text-field>
      </v-row>
      <v-row>
        <v-text-field label="IPK" v-model="mhs.ipk" variant="outlined"></v-text-field>
      </v-row>
      <v-row>
        <v-btn color="blue" @click="submitMahasiswa">Submit</v-btn>
      </v-row>
    </div>
  </v-container>
</template>

<script lang="ts">
import { Mahasiswa } from '@/model/Mahasiswa'
export default {
  data() {
    return {
      mhs: new Mahasiswa('1234', '', 0)
    }
  },
  methods: {
    submitMahasiswa() {
      if (!this.mhs.npm || !this.mhs.nama || !this.mhs.ipk) {
        alert('Field tertentu belum terisi!')
      } else if (this.mhs.ipk < 0 || this.mhs.ipk > 4) {
        alert('IPK harus diantara 0 sampai 4')
      } else {
        const confirmation = confirm('Apakah Anda yakin ingin menyimpan data?')
        if (confirmation) {
          alert('Data Mahasiswa ' + this.mhs.nama + ' berhasil disimpan')
          this.resetData()
        }
      }
    },
    resetData() {
      this.mhs = new Mahasiswa('', '', 0)
    }
  }
}
</script>

<style scoped>
h2 {
  padding-bottom: 30px;
}

.outer-box {
  border: 1px solid #ccc;
  padding: 80px; /* Mengurangi padding untuk tampilan yang lebih ramping */
  background-color: #f9f9f9; /* Ubah warna latar belakang menjadi abu-abu muda */
  border-radius: 10px; /* Tambahkan border-radius untuk sudut yang lebih lembut */
  box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.1); /* Tambahkan efek bayangan */
}
</style>
