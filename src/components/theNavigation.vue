<template>
  <div class="flex items-center gap-x-6 overflow-x-scroll pt-[38px]" >
    <navCard
    v-for="item in navigation"
    :key="item.id"
    :id="item.id"
    :title="item.title"
    :imgUrl="item.imgUrl"
    />
  </div>
</template>

<style scoped>

</style>

<script setup>
import navCard from './navCard.vue';

defineProps({
  navigation: Array,
})
</script>
