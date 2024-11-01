<template>
  <div class="grid grid-cols-3 gap-[30px]">
    <theCard
      v-for="item in card"
      :key="item.id"
      :id="item.id"
      :title="item.title"
      :imgUrl="item.imgUrl"
      :price="item.price"
      :weight="item.weight"
    />
  </div>
</template>

<script setup>
import TheCard from './theCard.vue'

defineProps({
  card: Array,
})
</script>
