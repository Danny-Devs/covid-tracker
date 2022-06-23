<script setup>
import { ref, onMounted } from 'vue'
import DataTitle from '../components/DataTitle.vue'
import DataBoxes from '../components/DataBoxes.vue'

const loading = ref(true)
const title = ref('Global')
const dataDate = ref('')
const stats = ref({})
const countries = ref([])

const fetchCovidData = async () => {
  const res = await fetch('https://api.covid19api.com/summary')
  const data = await res.json()
  dataDate.value = data.Date
  stats.value = data.Global
  countries.value = data.Countries
  loading.value = false
  // console.log(data)
}

onMounted(() => {
  fetchCovidData()
})
</script>

<template>
  <main v-if="!loading">
    <DataTitle :text="title" :dataDate="dataDate" />
    <DataBoxes :stats="stats" />
  </main>

  <main class="flex flex-col align-center justify-center text-center" v-else>
    <div class="text-gray-500 text-3xl mt-10 mb-6">Fetching data...</div>
    <img
      src="../assets/hourglass.gif"
      class="w-24 m-auto"
      alt="hourglass loading gif"
    />
  </main>
</template>
