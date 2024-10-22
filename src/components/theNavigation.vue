<template>
  <div class="flex items-center justify-between pt-[38px]">
    <navCard
    v-for="item in navigation"
    :key="item.id"
    :id="item.id"
    :title="item.title"
    :imgUrl="item.imgUrl"
    />
  </div>
</template>

<script setup>
import navCard from './navCard.vue';

defineProps({
  navigation: Array,
})
</script>
