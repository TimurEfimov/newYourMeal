<template>
  <div
    class="flex items-center bg-white border-solid border-2 border-white text-nowrap max-w-[121px] px-[14px] py-[9px] rounded-[50px] cursor-pointer transition hover:border-[#F86310]"
  >
    <img :src="imgUrl" alt="" />
    <h4 class="ml-[9px]">{{ title }}</h4>
  </div>
</template>
<script setup>
defineProps({
  id: Number,
  title: String,
  imgUrl: String,
})
</script>
