<template>
  <v-navigation-drawer expand-on-hover rail>
    <v-divider></v-divider>

    <v-list density="compact" nav>
      <v-list-item prepend-icon="mdi-folder" title="Home" :to="'/'"></v-list-item>
      <v-list-item prepend-icon="mdi-account-multiple" title="Dosen" :to="'/Dosen'"></v-list-item>
      <v-list-item prepend-icon="mdi-star" title="Mahasiswa" :to="'/Mahasiswa'"></v-list-item>
      <v-list-item prepend-icon="mdi-star" title="Ruangan" :to="'/Ruangan'"></v-list-item>
      <v-list-item
        prepend-icon="mdi-calendar"
        title="Jadwal Kuliah"
        :to="'/JadwalKuliah'"
      ></v-list-item>
      <v-list-item prepend-icon="mdi-phone" title="Kontak" :to="'/Kontak'"></v-list-item>
    </v-list>
  </v-navigation-drawer>

  <v-main style="height: 250px"></v-main>
</template>
<style scoped>
.v-navigation-drawer {
  background-color: #2196f3;
  color: #ffffff;
}
</style>
