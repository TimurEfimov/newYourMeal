<template>
  <div>
    <theHeader />
    <div class="container xl mx-auto">
      <theNavigation
        :navigation="navigation"
        @getNav="n => (navItem = n)"
        :navItem="navItem"
      />
      <h2 class="text-[40px] font-semibold mt-[50px] mb-6">Бургеры</h2>
      <div class="flex gap-[30px]">
        <theCart />
        <listCard :card="items[navItem]" />
      </div>
    </div>
  </div>
  <theFooter />
</template>

<style scoped></style>

<script setup>
import { watch, ref, defineProps, onMounted } from 'vue'
import axios from 'axios'
import theHeader from './components/theHeader.vue'
import theNavigation from './components/theNavigation.vue'
import theCart from './components/theCart.vue'
import listCard from './components/listCard.vue'
import theFooter from './components/theFooter.vue'

const navigation = ref([])
const items = ref([])
const navItem = ref('burgers')

const fetchNavigation = async () => {
  try {
    const { data } = await axios.get(
      'https://f0183f9cd8650d83.mokky.dev/navigation',
    )

    navigation.value = data
  } catch (err) {
    console.log(err)
  }
}

const fetchItems = async () => {
  try {
    const { data } = await axios.get(`https://f0183f9cd8650d83.mokky.dev/items`)

    items.value = data[0]
  } catch (err) {
    console.log(err)
  }
}

onMounted(() => {
  fetchNavigation(), fetchItems()
})
</script>
