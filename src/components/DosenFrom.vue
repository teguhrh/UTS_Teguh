<template>
  <v-container>
    <div class="outer-box">
      <h2>Entry Data Dosen</h2>
      <v-row>
        <v-text-field label="NIDN" v-model="dosen.nidn" variant="outlined"></v-text-field>
      </v-row>
      <v-row>
        <v-text-field label="Nama" v-model="dosen.nama" variant="outlined"></v-text-field>
      </v-row>
      <v-row>
        <v-btn color="blue" @click="submitDosen">Submit</v-btn>
      </v-row>
    </div>
  </v-container>
</template>

<script lang="ts">
import { Dosen } from '@/model/Dosen'

export default {
  data() {
    return {
      dosen: new Dosen('', '')
    }
  },
  methods: {
    submitDosen() {
      if (!this.dosen.nidn || !this.dosen.nama) {
        alert('Field NIDN dan Nama belum terisi')
      } else {
        alert('Data Dosen ' + this.dosen.nama + ' berhasil disimpan')
        this.dosen = new Dosen('', '')
      }
    }
  }
}
</script>

<style scoped>
h2 {
  padding-bottom: 30px;
  color: #000000;
}

.outer-box {
  border: 1px solid #ccc;
  padding: 100px;
  background-color: #f9f9f9;
  border-radius: 10px;
  box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.1);
}

.input-row {
  display: flex;
  justify-content: space-between;
  margin-bottom: 20px;
}

.input-row v-text-field {
  width: calc(50% - 10px);
}
</style>
