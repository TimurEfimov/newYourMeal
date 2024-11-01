<template>
  <div class="flex items-center gap-x-6 overflow-x-scroll pt-[38px]">
    <div
      v-for="item in navigation"
      :key="item.id"
      @click="$emit('getNav', item.value)"
      :class="{ 'bg-[#FFAB08] transition': item.value == navItem }"
      class="flex items-center bg-white border-solid border-2 border-white text-nowrap max-w-[121px] px-[14px] py-[9px] rounded-[50px] cursor-pointer transition hover:border-[#F86310]"
    >
      <img :src="item.imgUrl" alt="" />
      <h4 class="ml-[9px]">{{ item.title }}</h4>
    </div>
  </div>
</template>

<style scoped></style>

<script setup>
import { defineProps } from 'vue';

defineProps({
  navigation: Array,
  navItem: String
})
</script>
