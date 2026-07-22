<script setup>
// Progress within one exercise: <Steps n="2" total="5" />
defineProps({
  n: { type: [Number, String], default: 1 },
  total: { type: [Number, String], default: 3 },
})
</script>

<template>
  <span class="steps">
    <i v-for="i in Number(total)" :key="i" :class="{ on: i <= Number(n) }" />
  </span>
</template>
