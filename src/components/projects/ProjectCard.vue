<template>
  <div class="card">
    <h5>{{ title }}</h5>
    <p>{{ description }}</p>
    <div class="project-buttons">
      <slot name="icons"></slot>
    </div>
  </div>
</template>

<script lang="ts" setup>
defineProps({
  title: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    required: true,
  },
});
</script>

<style scoped>
.card {
  padding: 16px;
  border: 1px solid #ddd;
  border-radius: 8px;
  margin-bottom: 16px;
  background-color: #fff;
}
.card h5 {
  margin-bottom: 8px;
  font-size: 18px;
  font-weight: bold;
}
.card p {
  font-size: 14px;
  line-height: 1.5;
  color: #555;
}
.project-buttons {
  margin-top: 12px;
  display: flex;
  gap: 8px;
}
</style>
