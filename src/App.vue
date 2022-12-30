<script setup>
import { ref, watch } from 'vue'

const state = ref({ deep: false })

function onClick() {
  state.value.deep = !state.value.deep
}

let count = 0

watch(() => [state.value.deep], () => {
  state.value = { deep: false }
  console.log('watch', ++count)
})
</script>

<template>
  <button @click="onClick">click: {{ state.deep }}</button>
</template>
