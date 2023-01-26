<template>
    <div class="h-16 bg-white flex">
        <div class="w-16 h-16 h-full bg-yellow-400 grid place-items-center cursor-pointer mr-10">
            <img src="@/assets/menu.svg" alt="" />
        </div>
        <div class="flex flex-col justify-center">
            <p class="text-lg leading-none uppercase text-[#00074e] font-bold mb-2">Desa Setu</p>
            <p class="text-lg leading-none uppercase text-[#00074e] font-bold ">Kabupaten Bogor</p>
        </div>
        <div class="flex items-center h-full ml-auto pr-20">
            <a class="text-lg text-[#001b85] mx-4 cursor-pointer">Profile Desa</a>
            <a class="text-lg text-[#001b85] mx-4 cursor-pointer">Berita</a>

            <div class="border-l border-zinc-700 h-[60%] flex items-center px-4 ml-10">
                <input placeholder="Search" class="outline-none h-full w-22" />
                <img src="@/assets/search.svg" class="w-4 ml-4" alt=""/>
            </div>
        </div>
    </div>
</template>
