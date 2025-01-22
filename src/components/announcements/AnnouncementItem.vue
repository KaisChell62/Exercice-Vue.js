<template>
  <div class="announcement-item">
    <h5>{{ title }}</h5>
    <p>{{ description }}</p>
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
.announcement-item {
  padding: 16px;
  border: 1px solid #ddd;
  border-radius: 8px;
  margin-bottom: 16px;
  background-color: #f9f9f9;
}
.announcement-item h5 {
  margin-bottom: 8px;
  font-size: 18px;
  font-weight: bold;
}
.announcement-item p {
  font-size: 14px;
  line-height: 1.5;
  color: #555;
}
</style>
