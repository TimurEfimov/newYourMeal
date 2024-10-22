<template>
  <div>
    <theHeader />
    <div class="container xl mx-auto">
      <theNavigation :navigation="navigation" />
    </div>
  </div>
</template>

<script setup>
import { watch, ref, defineProps } from 'vue';
import axios from 'axios';
import theHeader from './components/theHeader.vue'
import theNavigation from './components/theNavigation.vue'

const navigation = ref([])

const fetchNavigation = async () => {
  try {
    const {data} = await axios.get('https://f0183f9cd8650d83.mokky.dev/navigation')

    navigation.value = data
  } catch (err) {
    console.log(err)
  }
}

watch(fetchNavigation)
</script>
