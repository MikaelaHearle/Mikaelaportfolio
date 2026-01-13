<template>
  <div class="content-block">
    <slot name="title"></slot>
    <slot />
  </div>
</template>

<script setup lang="ts">
defineSlots<{
  title?: () => any;
  default?: () => any;
}>();
</script>

<style scoped>
.content-block {
  padding: 2rem 1rem;
}

@media (min-width: 1024px) {
  .content-block {
    padding: 2rem 10rem;
  }
}

@media (min-width: 2560px) {
  .content-block {
    padding: 2rem 30rem;
  }
}
</style>
