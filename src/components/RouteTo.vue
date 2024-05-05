<script setup lang="ts">
defineProps<{
  lat: number,
  lng: number
}>()
</script>

<template>
  <a target="_blank" :href="'https://maps.google.com/?q=' + lat + ',' + lng">Route</a>
</template>
