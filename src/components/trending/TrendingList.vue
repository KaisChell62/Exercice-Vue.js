<template>
  <div class="trending-list">
    <h4>{{ title }}</h4>
    <div class="background-box">
      <TrendingItem
        v-for="(trend, index) in trends"
        :key="index"
        :avatar="trend.avatar"
        :username="trend.username"
        :description="trend.description"
      />
    </div>
  </div>
</template>

<script lang="ts" setup>
import TrendingItem from './TrendingItem.vue';

defineProps({
  title: {
    type: String,
    required: true,
  },
  trends: {
    type: Array,
    required: true,
    default: () => [],
  },
});
</script>

<style scoped>
.trending-list {
  margin-bottom: 24px;
}
.background-box {
  padding: 16px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: #f9f9f9;
}
</style>
