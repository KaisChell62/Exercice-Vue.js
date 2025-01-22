<template>
  <div class="announcements">
    <h4>{{ title }}</h4>
    <div class="announcement-list">
      <AnnouncementItem
        v-for="(announcement, index) in announcements"
        :key="index"
        :title="announcement.title"
        :description="announcement.description"
      />
    </div>
  </div>
</template>

<script lang="ts" setup>
import AnnouncementItem from './AnnouncementItem.vue';

defineProps({
  title: {
    type: String,
    required: true,
  },
  announcements: {
    type: Array,
    required: true,
    default: () => [],
  },
});
</script>

<style scoped>
.announcements {
  margin-bottom: 24px;
}
.announcement-list {
  margin-top: 16px;
}
</style>
