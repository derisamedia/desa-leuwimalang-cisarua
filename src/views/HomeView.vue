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
        “Terwujudnya Desa Setu Yang Sejahtera dan Mandiri, ditopang Kinerja
        Aparatur yang Profesional dalam Kerangka Budaya Bangsa didasari Keimanan
        dan Ketaqwaan”
      </p>
      <p class="text-lg font-semibold">Misi</p>
      <ul>
        <li>
          1. Mengembangkan system Pemerintahan Desa yang bersih dan profesional
          serta berorientasi pada pelayanan publik dengan prinsif kerja ikhlas,
          lakukan sekarang dan siap turun ke lapangan;
        </li>
        <li>
          2. Meningkatkan dan memantapkan system perencanaan pembangunan desa
          melalui pengoptimalan mekanisme musyawarah pembangunan desa dengan
          melibatkan seluruh steackholder yang ada;
        </li>
        <li>
          3. Membuat skala prioritas untuk kegiatan-kegiatan pembangunan yang
          akan dilaksanakan baik pembangunan fisik atau non fisik, seperti
          infrastruktur, perekonomian, keagamaan, Pendidikan dan kesehatan;
        </li>
        <li>
          4. Meningkatkan kemampuan dan peran serta aktif masyarakat dalam
          mengelola pembangunan berkelanjutan secara efisisen dan efektif dengan
          memanfaatkan potensi sumber daya yang ada, baik sumber daya alam
          maupun sumberdaya manusia;
        </li>
        <li>
          5. Meningkatkan kemampuan dan pemberdayaan Lembaga-lembaga
          kemasyarakatan yang ada didesa atau lebih mendinamisasi dan mendukung
          seluruh proses pembangunan;
        </li>
        <li>
          6. Mendorong majunya Pendidikan formal maupun nonformal seperti
          pesantren, LPK, diklat serta penyuluhan pertanian yang mudah diakses
          dan dinikmati seluruh warga masyarakat, guna menghasilkan insan
          intelektual, berakhlak mulia, inovatif dan entrepreneur;
        </li>
        <li>
          7. Menyalurkan segala bentuk bantuan dari Pemerintah Kabupaten,
          Provinsi dan Pusat sesuai dengan peruntukannya dan mencegah terjadinya
          penyimpangan dan kebocoran;
        </li>
        <li>
          8. Menjalin sinergitas dengan instansi atau Lembaga terkait dan pihak
          swasta guna optimalisasi suatu tujuan lebih baik dan lebih maksimal;
        </li>
        <li>
          9. Responsive dan aspiratif atas segala bentuk kebutuhan atau
          keinginan dan permasalahan yang terjadi ditengah masyarakat yang
          majemuk dan dinamis;
        </li>
        <li>
          10. Membina dan memantapkankehidupan gotong royongsebagai basis dan
          modal dasar pembangunan desa, yang pada hakikatnyajuga merupakan
          karakter dasar dari masyarakat desa dan juga bangsa Indonesia.
        </li>
      </ul>

      <p class="text-3xl font-semibold my-4">Struktur Desa</p>
      <img src="@/assets/struktur.jpg" alt="" />
    </div>
  </main>
</template>

<style>
body {
  background: #f1f1f1;
}
</style>
