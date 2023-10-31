<script setup>
import Header from "../components/Header.vue";
import Banner from "../components/Banner.vue";
import Sidebar from "../components/Sidebar.vue";
</script>

<template>
  <Header />
  <Banner />

  <main class="flex">
    <Sidebar />

    <div class="flex-1 p-10">
      <p class="text-3xl font-semibold">Visi & Misi Desa</p>
      <p class="text-lg font-semibold">Visi</p>
      <p>
        “Terwujudnya Desa Leuwimalang Menjadi Desa Mandiri Berlandaskan pada Tata Kelola Pemerintahan Desa yang Profesional dan Bermartabat”
      </p>
      <p class="text-lg font-semibold">Misi</p>
      <ul>
        <li>
          1. Meningkatkan Penyelenggaraan Tata Kelola Pemerintahan Yang Akuntabel;
        </li>
        <li>
          2. Meningkatkan Perekonomian Berbasis Kerakyatan;
        </li>
        <li>
          3. Meningkatkan Interaksi Antar Lembaga Formal dan Non Formal;
        </li>
        <li>
          4. Meningkatkan Kualitas Hidup dan Kebudayaan;
        </li>
        <li>
          5. Meningkatkan Pembangunan Infrastruktur Desa;
        </li>
        <li>
          6. Melestarikan Sumber Daya Alam dan Lingkungan;
        </li>
        <li>
          7. Meningkatkan kehidupan Desa yang religius dan dinamis, dalam segi keagamaan dan kebudayaan asli daerah;
        </li>
      </ul>
    </div>
  </main>
</template>

<style>
body {
  background: #f1f1f1;
}
</style>
