<template>
  <div class="trend">
    <figure>
      <img :src="avatar" alt="avatar" class="avatar" />
    </figure>
    <div class="trend-details">
      <h6>{{ username }}</h6>
      <p>{{ description }}</p>
    </div>
  </div>
</template>

<script lang="ts" setup>
defineProps({
  avatar: {
    type: String,
    required: true,
  },
  username: {
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
.trend {
  display: flex;
  align-items: center;
  gap: 16px;
  padding: 8px 0;
  border-bottom: 1px solid #ddd;
}
.trend:last-child {
  border-bottom: none;
}
.avatar {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  object-fit: cover;
}
.trend-details h6 {
  margin: 0;
  font-size: 16px;
  font-weight: bold;
}
.trend-details p {
  margin: 0;
  font-size: 14px;
  color: #666;
}
</style>
