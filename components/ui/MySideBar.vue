<script setup lang="ts">
defineProps<{
  ui: {
    base: string;
  };
}>();
</script>

<template>
  <div :class="`sidebar ${ui.base}`">
    <slot />
  </div>
</template>

<style scoped>
.sidebar {
  padding: 1rem;
  height: calc(100vh - 3rem);
  border-right: 1px solid #ddd;
}
</style>
