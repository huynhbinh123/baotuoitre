<template>
  <header class="flex shadow bg-red-600">
    <div
      class="container max-w-7xl mx-auto px-4 py-3 flex justify-between items-center"
    >
      <nuxt-link to="/">
        <img src="/logottonew.svg" alt="" class="h-10" />
      </nuxt-link>
      <nav class="space-x-4 flex items-center text-white font-medium">
        <a
          href="https://podcast.tuoitre.vn/"
          target="_blank"
          class="flex items-center gap-1"
        >
          <Mic class="w-4 h-4" />
          Podcast
        </a>
        <a
          href="https://www.youtube.com/channel/UC47WI-kZXFf0H_f7pvaNCEQ"
          target="_blank"
          class="flex items-center gap-1"
        >
          <Youtube class="w-4 h-4" />
          Youtube
        </a>
        <a
          href="https://tuoitre.vn/can-biet.htm"
          class="flex items-center gap-1"
        >
          <Info Megaphone class="w-4 h-4" />
          Cần biết
        </a>
        <a
          href="https://raovat.tuoitre.vn/"
          target="_blank"
          class="flex items-center gap-1"
        >
          <Megaphone class="w-4 h-4" />
          Rao vặt
        </a>
        <Search class="w-4 h-4" />
        <CircleUser class="w-4 h-4 cursor-pointer" @click="goToLogin" />
        <a href="https://sso.tuoitre.vn/dang-ky-tuoi-tre-sao" target="_blank">
          <button class="bg-blue-500 p-1 rounded-md">
            Đăng ký tuổi trẻ sao
          </button>
        </a>
        <button>
          <ShieldQuestion class="w-4 h-4" />
        </button>
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

const router = useRouter();

const goToLogin = () => {
  router.push("/login");
};
</script>
