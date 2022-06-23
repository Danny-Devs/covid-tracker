<script setup>
const props = defineProps({
  stats: { type: Object, required: true },
})
</script>

<template>
  <div class="grid md:grid-cols-2 gap-4">
    <!-- Box 1 -->
    <div class="shadow-md bg-blue-100 p-10 text-center rounded">
      <h3 class="text-3xl text-blue-900 font-bold mb-4">Cases</h3>

      <div class="text-2xl mb-4">
        <span class="font-bold">New:</span>
        {{ props.stats.NewConfirmed.toLocaleString('en-US') }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Total:</span>
        {{ props.stats.TotalConfirmed.toLocaleString('en-US') }}
      </div>
    </div>
    <!-- Box 2 -->
    <div class="shadow-md bg-blue-100 p-10 text-center rounded">
      <h3 class="text-3xl text-blue-900 font-bold mb-4">Deaths</h3>

      <div class="text-2xl mb-4">
        <span class="font-bold">New:</span>
        {{ props.stats.NewDeaths.toLocaleString('en-US') }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Total:</span>
        {{ props.stats.TotalDeaths.toLocaleString('en-US') }}
      </div>
    </div>
  </div>
</template>

<style scoped></style>
