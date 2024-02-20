<script setup lang="ts">
defineProps<{
  zIndex: number;
}>();
</script>

<template>
  <header class="header" :style="{ zIndex }">
    <slot />
  </header>
</template>

<style scoped>
.header {
  top: 0;
  padding: 0.5rem 1.5rem;
  position: sticky;
  border-bottom: 1px solid #ddd;
  background-color: white;
}
</style>
