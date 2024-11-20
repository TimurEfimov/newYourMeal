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
        <theCart
          :cart="busket"
          :totalPrice="totalPrice"
          :totalBusket="totalBusket"
          @addToBusket="id => plusBusket(id)"
          @minusBusket="id => minusBusket(id)"
        />
        <listCard
          :card="items[navItem]"
          @addToCart="item => addToBusket(item)"
        />
      </div>
    </div>
  </div>
  <theFooter />
</template>

<style scoped></style>

<script setup>
import { watch, ref, defineProps, onMounted, computed } from 'vue'
import axios from 'axios'
import theHeader from './components/theHeader.vue'
import theNavigation from './components/theNavigation.vue'
import theCart from './components/theCart.vue'
import listCard from './components/listCard.vue'
import theFooter from './components/theFooter.vue'

const navigation = ref([])
const items = ref([])
const busket = ref([])
const navItem = ref('burgers')

const totalPrice = computed(() =>
  busket.value.reduce((acc, item) => acc + (item.price * item.count), 0),
)

const totalBusket = computed(() => busket.value.length)

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

const addToBusket = item => {
  if (busket.value.length >= 1) {
    for (let i of busket.value) {
      if (i.id === item.id) {
        i.count++
        console.log(52)
      } else {
        item.count = 1
        busket.value.push(item)
        console.log(42)
      }
      break
    }
  } else {
    item.count = 1
    busket.value.push(item)
  }
}

const plusBusket = id => {
  console.log(id)
  for (let i of busket.value) {
    if (i.id === id) {
      i.count++
    }
  }
}

const minusBusket = id => {
  console.log(id)
  for (let i of busket.value) {
    if (i.id === id) {
      i.count--
      if (i.count < 1) {
        let ind = busket.value.indexOf(i)
        busket.value.splice(ind, 1)
      }
    }
  }
}

onMounted(() => {
  fetchNavigation(), fetchItems()
})
</script>
