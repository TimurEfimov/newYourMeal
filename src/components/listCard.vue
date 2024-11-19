<template>
  <div class="grid grid-cols-3 gap-[30px]">
    <div
      class="bg-white rounded-[18px] max-w-[300px] p-3"
      v-for="item in card"
      :key="item.id"
    >
      <img class="max-w-[276px] mb-4" :src="item.imgUrl" alt="" />
      <b class="text-2xl font-semibold">{{ item.price }}₽</b>
      <h6 class="mt-2 mb-[29px]">{{ item.title }}</h6>
      <p class="text-[#B1B1B1] font-semibold">{{ item.weight }}г</p>
      <button
        class="mt-2 bg-[#F2F2F3] text-center px-24 py-3 rounded-xl transition hover:bg-[#FFAB08] hover:text-white"
        @click="$emit('addToCart', item)"
      >
        Добавить
      </button>
    </div>
  </div>
</template>

<script setup>
defineProps({
  card: Array,
  addToCart: Function,
})
</script>
