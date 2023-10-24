<template>
  <div class="h-16 bg-green-700 flex">
    <!-- <div
      class="w-16 h-16 h-full bg-green-500 grid place-items-center cursor-pointer mr-10"
    >
      <img src="@/assets/menu.svg" alt="" />
    </div> -->
    <div class="flex flex-col ml-5 justify-center">
      <!-- Sesuaikan nama desa masing-masing -->
      <p class="text-lg leading-none uppercase text-white font-bold mb-2">
        Desa Setu
      </p>
      <p class="text-lg leading-none uppercase text-white font-bold">
        Kabupaten Bogor
      </p>
    </div>
    <div class="flex items-center h-full ml-auto pr-20">
      <a class="text-lg text-white mx-4 cursor-pointer">
        <router-link to="/">Home</router-link>
      </a>
      <a class="text-lg text-white mx-4 cursor-pointer">
        <router-link to="/map">Peta Desa</router-link>
      </a>

      <a class="text-lg text-white mx-4 cursor-pointer">
        <router-link to="/about">Tentang Desa</router-link>
      </a>

      <!-- <div
        class="border-l border-zinc-700 h-[60%] flex items-center px-4 ml-10"
      >
        <input placeholder="Search" class="outline-none h-full w-22" />
        <img src="@/assets/search.svg" class="w-4 ml-4" alt="" />
      </div> -->
    </div>
  </div>
</template>
