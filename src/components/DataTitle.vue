<script setup>
import { format, parseISO } from 'date-fns'
import { computed } from 'vue'

const props = defineProps({
  text: { type: String, required: true },
  dataDate: { type: String, required: true },
})

const timestamp = computed(() => {
  return format(parseISO(props.dataDate), 'MMMM do, yyyy, h:mm:ss aaa')
})
</script>

<template>
  <div class="text-center">
    <h2 class="text-3xl font-bold">{{ text }}</h2>
    <div class="text-2xl mt-4 mb-10">
      {{ timestamp }}
    </div>
  </div>
</template>

<style scoped></style>
