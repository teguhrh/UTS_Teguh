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
        alert('field tertentu belum terisi!')
      } else if (this.mhs.ipk < 0 || this.mhs.ipk > 4) {
        alert('IPK harus diantara 0 sampai 4')
      } else {
        alert('Data Mahasiswa ' + this.mhs.nama + ' berhasil disimpan')
        this.mhs = new Mahasiswa('', '', 0)
      }
    }
  }
}
</script>

<style scoped>
h2 {
  padding-bottom: 30px;
}

.outer-box {
  border: 2px solid #ccc;
  padding: 80px;
}
</style>
