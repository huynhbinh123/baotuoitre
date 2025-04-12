<template>
  <header class="flex shadow bg-red-600">
    <div
      class="container max-w-7xl mx-auto px-4 py-3 flex justify-between items-center"
    >
      <nuxt-link to="/">
        <img src="/logottonew.svg" alt="" class="h-10" />
      </nuxt-link>
      <nav class="space-x-4 flex items-center text-white font-medium">
        <a href="/podcast" class="flex items-center gap-1">
          <Mic class="w-4 h-4" />
          Podcast
        </a>
        <a href="/youtube" class="flex items-center gap-1">
          <Youtube class="w-4 h-4" />
          Youtube
        </a>
        <a href="/can-biet" class="flex items-center gap-1">
          <Info class="w-4 h-4" />
          Cần biết
        </a>
        <a href="/rao-vat" class="flex items-center gap-1">
          <Megaphone class="w-4 h-4" />
          Rao vặt
        </a>
        <Search class="w-4 h-4" />
        <CircleUser class="w-4 h-4" />
        <button class="bg-blue-500 p-1 rounded-md">Đăng ký tuổi trẻ sao</button>
        <ShieldQuestion class="w-4 h-4" />
      </nav>
    </div>
  </header>
</template>

<script setup>
import {
  Mic,
  Youtube,
  Info,
  Megaphone,
  Search,
  CircleUser,
  ShieldQuestion,
} from "lucide-vue-next";
</script>
