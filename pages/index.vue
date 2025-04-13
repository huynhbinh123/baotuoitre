<template>
  <nav class="bg-white border-t border-b py-2 shadow">
    <div class="max-w-7xl mx-auto px-4">
      <div
        class="flex flex-wrap gap-4 text-black justify-between font-medium text-xs"
      >
        <a href="/"><House class="w-4 h-4 text-red-600" /></a>
        <NuxtLink
          v-for="(item, index) in items"
          :key="index"
          :to="`/${item.slug}`"
          class="text-black-700 hover:text-red-600 transition uppercase"
        >
          {{ item.name }}
        </NuxtLink>
      </div>
    </div>
  </nav>

  <nav class="bg-white py-4 shadow">
    <div class="max-w-7xl mx-auto px-4">
      <div class="grid grid-cols-12 gap-6">
        <!-- 🧭 Cột trái: Danh sách tiêu đề nhỏ -->
        <div class="col-span-2 space-y-2 overflow-y-auto max-h-[500px]">
          <ul class="space-y-1">
            <li
              v-for="(value, index) in values"
              :key="index"
              class="text-sm hover:text-red-600 text-gray-600 leading-snug border-t py-2"
            >
              <nuxt-link :to="`${value.slug}`">{{
                value.description
              }}</nuxt-link>
            </li>
          </ul>
        </div>

        <!-- 📰 Cột giữa: Tin nổi bật và tin nhỏ -->
        <div class="col-span-7 space-y-6 border-l border-r border-gray-300">
          <!-- Tin nổi bật -->
          <div class="grid grid-cols-3 gap-4 items-start mx-2">
            <!-- Ảnh (2 cột) -->
            <div class="col-span-2">
              <NuxtLink :to="`/${datas[0].slug}`" class="block">
                <img
                  :src="datas[0].img"
                  alt=""
                  class="w-full h-60 object-cover"
                />
              </NuxtLink>
            </div>

            <!-- Nội dung (1 cột) -->
            <div class="col-span-1 space-y-2">
              <NuxtLink
                :to="`/${datas[0].slug}`"
                class="hover:text-red-600 block"
              >
                <h2 class="font-semibold text-base leading-snug">
                  {{ datas[0].name }}
                </h2>
              </NuxtLink>
              <p class="text-sm text-gray-600">{{ datas[0].desc }}</p>
            </div>
          </div>

          <!-- Danh sách tin nhỏ -->
          <ul class="grid grid-cols-3 gap-4 mx-2">
            <li
              v-for="(data, index) in datas.slice(1)"
              :key="index"
              class="space-y-2"
            >
              <NuxtLink :to="`/${data.slug}`" class="block group">
                <img :src="data.img" alt="" class="w-full h-40 object-cover" />
              </NuxtLink>
              <NuxtLink :to="`/${data.slug}`" class="block group">
                <h3
                  class="text-sm font-medium text-gray-800 group-hover:text-red-600"
                >
                  {{ data.name }}
                </h3>
              </NuxtLink>
            </li>
          </ul>
        </div>

        <!-- 📸 Cột phải: Ảnh quảng cáo hoặc banner -->
        <div class="col-span-3 space-y-4">
          <img src="/anh1.png" alt="" class="w-full shadow" />
          <img src="/anh2.png" alt="" class="w-full shadow" />
        </div>
      </div>
    </div>
  </nav>

  <nav class="bg-white py-4 border-y border">
    <div class="max-w-7xl mx-auto px-4 flex justify-between items-center">
      <!-- Bên trái -->
      <div class="flex items-center gap-4">
        <nuxt-link to="/tin-moi-nhat">
          <button class="border text-sm font-medium p-2 bg-gray-100">
            Tin mới nhất
          </button>
        </nuxt-link>
        <TrendingUp class="text-red-600" />
        <ul class="flex gap-2">
          <li v-for="(a, index) in as" :key="index">
            <NuxtLink
              :to="`/${a.slug}`"
              class="text-gray-600 px-3 py-1 rounded bg-gray-100 hover:bg-gray-200 text-base font-medium flex items-center justify-center text-center"
            >
              {{ a.name }}
            </NuxtLink>
          </li>
        </ul>
      </div>

      <!-- Bên phải -->
      <div class="flex gap-2">
        <button
          class="flex border text-gray-600 px-4 bg-gray-100 py-1 hover:opacity-80"
        >
          <Phone class="mr-1 w-3" />
          Hotline
        </button>
        <button
          class="flex border text-gray-600 px-4 bg-gray-100 py-1 hover:opacity-80"
        >
          <Newspaper class="mr-1 w-3" />
          Đặt báo
        </button>
        <button
          class="flex border text-gray-600 px-4 bg-gray-100 py-1 hover:opacity-80"
        >
          <Volume class="mr-1 w-3" />
          Quảng cáo
        </button>
      </div>
    </div>
  </nav>

  <nav class="bg-white mt-10">
    <div class="max-w-7xl mx-auto px-4 grid grid-cols-12">
      <div class="col-span-7 pr-8">
        <ul>
          <li v-for="(b, index) in bs" :key="index" class="border-t">
            <div class="flex my-6">
              <NuxtLink :to="b.slug" class="w-full">
                <img :src="b.img" alt="" class="w-full h-auto object-cover" />
              </NuxtLink>
              <div class="flex-col p-4">
                <NuxtLink :to="b.slug" class="hover:text-red-600 block">
                  <h2
                    class="text-black text-lg font-semibold hover:text-red-600"
                  >
                    {{ b.name }}
                  </h2>
                </NuxtLink>

                <p class="text-gray-600">
                  {{ b.desc }}
                </p>
              </div>
            </div>
          </li>
        </ul>
      </div>

      <div class="col-span-5">
        <div
          class="p-6 bg-gradient-to-b from-[rgba(211,233,250,1)] to-white border rounded-md mt-4"
        >
          <div class="flex justify-between pb-2 border-b">
            <span class="flex">
              <CircleSmall class="text-red-500" />
              <nuxt-link to="/" class="font-medium">CHỦ ĐỀ NỔI BẬT</nuxt-link>
            </span>
            <nuxt-link to="/" class="text-blue-500 font-medium"
              >Tất cả</nuxt-link
            >
          </div>
          <div class="mt-2 flex gap-4 overflow-x-auto scroll-smooth pb-2">
            <nuxtLink
              :to="c.slug"
              v-for="(c, index) in cs"
              :key="index"
              class="min-w-[60%] flex-shrink-0 bg-gray-50"
            >
              <img :src="c.img" alt="" class="w-full h-40 object-cover" />
              <p class="font-medium text-xl hover:text-red-500">
                {{ c.desc }}
              </p>
            </nuxtLink>
          </div>
        </div>

        <div
          class="p-6 bg-gradient-to-b from-[rgba(211,233,250,1)] to-white border rounded-md mt-4"
        >
          <div class="flex justify-between pb-2 border-b">
            <span class="flex">
              <CircleSmall class="text-red-500" />
              <nuxt-link to="/" class="font-medium">CHỦ ĐỀ NỔI BẬT</nuxt-link>
            </span>
            <nuxt-link to="/" class="text-blue-500 font-medium"
              >Tất cả</nuxt-link
            >
          </div>
          <div class="mt-2 flex gap-4 overflow-x-auto scroll-smooth pb-2">
            <nuxtLink
              :to="c.slug"
              v-for="(c, index) in cs"
              :key="index"
              class="min-w-[60%] flex-shrink-0 bg-gray-50"
            >
              <img :src="c.img" alt="" class="w-full h-40 object-cover" />
              <p class="font-medium text-xl hover:text-red-500">
                {{ c.desc }}
              </p>
            </nuxtLink>
          </div>
        </div>

        <div
          class="p-6 bg-gradient-to-b from-[rgba(211,233,250,1)] to-white border rounded-md mt-4"
        >
          <div class="flex justify-between pb-2 border-b">
            <span class="flex">
              <CircleSmall class="text-red-500" />
              <nuxt-link to="/" class="font-medium">CHỦ ĐỀ NỔI BẬT</nuxt-link>
            </span>
            <nuxt-link to="/" class="text-blue-500 font-medium"
              >Tất cả</nuxt-link
            >
          </div>

          <div class="mt-2 flex gap-4 overflow-x-auto scroll-smooth pb-2">
            <nuxtLink
              :to="c.slug"
              v-for="(c, index) in cs"
              :key="index"
              class="min-w-[60%] flex-shrink-0 bg-gray-50"
            >
              <img :src="c.img" alt="" class="w-full h-40 object-cover" />
              <p class="font-medium text-xl hover:text-red-500">
                {{ c.desc }}
              </p>
            </nuxtLink>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
const { data: items } = await useFetch("/api/data/nav");
const { data: values } = await useFetch("/api/data/content1");
const { data: datas } = await useFetch("/api/data/content2");
const { data: as } = await useFetch("/api/data/a");
const { data: bs } = await useFetch("/api/data/b");
const { data: cs } = await useFetch("/api/data/c");
import {
  House,
  Phone,
  Newspaper,
  Volume,
  TrendingUp,
  CircleSmall,
} from "lucide-vue-next";
</script>
<style scoped>
/* Thay đổi kích thước thanh cuộn */
.col-span-2::-webkit-scrollbar {
  width: 6px; /* Điều chỉnh độ rộng của thanh cuộn theo ý muốn */
}

.col-span-2::-webkit-scrollbar-thumb {
  background-color: #b3b0b0; /* Màu của phần tay nắm thanh cuộn */
  border-radius: 10px; /* Bo tròn góc của tay nắm */
}

.col-span-2::-webkit-scrollbar-thumb:hover {
  background-color: #555; /* Màu khi hover vào tay nắm */
}
</style>
