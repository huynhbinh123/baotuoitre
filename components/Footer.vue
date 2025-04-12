<template>
  <footer>
    <div class="bg-gray-50 border-b-2 border-red-600 mb-6">
      <div
        class="container mx-auto h-20 flex items-center justify-center gap-6 text-sm text-gray-700 font-medium"
      >
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
    <div
      class="container mx-auto h-20 flex items-center justify-center gap-6 text-sm"
    >
      <img src="/tuoitrefooter.png" alt="" class="h-20" />
      <div class="block py-4">
        <p>Tổng biên tập: Lê Thế Chữ</p>
        <p>Giấy phép hoạt động báo điện tử tiếng Việt, tiếng Anh</p>
        <p>Số 561/GP-BTTTT, cấp ngày 25-11-2022.</p>
        <p>Thông tin tòa soạn - Thành Đoàn TP.HCM</p>
      </div>
      <div>
        <p>Tổng biên tập: Lê Thế Chữ</p>
        <p>Giấy phép hoạt động báo điện tử tiếng Việt, tiếng Anh</p>
        <p>Số 561/GP-BTTTT, cấp ngày 25-11-2022.</p>
        <p>Thông tin tòa soạn - Thành Đoàn TP.HCM</p>
      </div>
      <div>
        <p>Tổng biên tập: Lê Thế Chữ</p>
        <p>Giấy phép hoạt động báo điện tử tiếng Việt, tiếng Anh</p>
        <p>Số 561/GP-BTTTT, cấp ngày 25-11-2022.</p>
        <p>Thông tin tòa soạn - Thành Đoàn TP.HCM</p>
      </div>
    </div>
    <p class="container mx-auto mt-6 text-xs text-center text-gray-500">
      © Copyright 2025 TuoiTre Online, All rights reserved ® Tuổi Trẻ Online giữ
      bản quyền nội dung trên website này
    </p>
  </footer>
</template>

<script setup>
const { data: items } = await useFetch("/api/data/nav");
</script>
