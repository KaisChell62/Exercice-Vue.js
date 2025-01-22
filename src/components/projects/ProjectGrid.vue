<template>
  <div class="project-grid">
    <slot></slot>
  </div>
</template>

<script lang="ts" setup>
</script>

<style scoped>
.project-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 16px;
  margin-top: 16px;
}
</style>
