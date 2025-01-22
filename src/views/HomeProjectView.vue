<script lang="ts" setup>
import ProjectGrid from "../components/projects/ProjectGrid.vue";
import ProjectCard from "../components/projects/ProjectCard.vue";
import Announcements from "../components/announcements/Announcements.vue";
import TrendingList from "../components/trending/TrendingList.vue";

// Données dynamiques pour les projets (7 projets)
const projects = [
  { title: "Super Cool Project", description: "Project description 1." },
  { title: "Awesome Web App", description: "Project description 2." },
  { title: "Revolutionary Design", description: "Project description 3." },
  { title: "Next-Gen AI", description: "Project description 4." },
  { title: "Blockchain Explorer", description: "Project description 5." },
  { title: "Eco-Friendly Initiative", description: "Project description 6." },
  { title: "Open Source Platform", description: "Project description 7." },
];

// Données dynamiques pour les annonces (8 annonces)
const announcements = [
  { title: "Site Maintenance", description: "Details about site maintenance." },
  { title: "Community Share Day", description: "Details about the event." },
  { title: "Updated Privacy Policy", description: "Details about the new policy." },
  { title: "New Feature Launch", description: "Exciting new feature update." },
  { title: "System Upgrade", description: "System upgrade scheduled soon." },
  { title: "Service Outage Notice", description: "Brief service interruption notice." },
  { title: "Customer Support Update", description: "New support hours." },
  { title: "Upcoming Webinar", description: "Join our next webinar session." },
];

// Données dynamiques pour les tendances (7 éléments Trending)
const trends = [
  { avatar: "https://robohash.org/1.png?set=set4", username: "@tegan", description: "World Peace Builder" },
  { avatar: "https://robohash.org/2.png?set=set4", username: "@morgan", description: "Super cool Project" },
  { avatar: "https://robohash.org/3.png?set=set4", username: "@kindall", description: "Life Changing App" },
  { avatar: "https://robohash.org/4.png?set=set4", username: "@alex", description: "No Traffic Maker" },
  { avatar: "https://robohash.org/5.png?set=set4", username: "@emma", description: "Creative Thinker" },
  { avatar: "https://robohash.org/6.png?set=set4", username: "@chris", description: "Tech Innovator" },
  { avatar: "https://robohash.org/7.png?set=set4", username: "@sarah", description: "Sustainability Advocate" },
];

// Données dynamiques pour les utilisateurs (9 utilisateurs)
const users = [
  { name: "Alice", email: "alice@example.com", role: "Administrator" },
  { name: "Bob", email: "bob@example.com", role: "Editor" },
  { name: "Charlie", email: "charlie@example.com", role: "Viewer" },
  { name: "Diana", email: "diana@example.com", role: "Moderator" },
  { name: "Ethan", email: "ethan@example.com", role: "Contributor" },
  { name: "Fiona", email: "fiona@example.com", role: "Reviewer" },
  { name: "George", email: "george@example.com", role: "Support" },
  { name: "Hannah", email: "hannah@example.com", role: "Admin Assistant" },
  { name: "Ivy", email: "ivy@example.com", role: "Project Manager" },
];
</script>

<template>
  <div class="dashboard-container">
    <!-- Section des projets -->
    <section class="projects-section">
      <h2>Your Projects</h2>
      <ProjectGrid>
        <ProjectCard
          v-for="(project, index) in projects"
          :key="index"
          :title="project.title"
          :description="project.description"
        >
          <template #icons>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
              <title>star-plus-outline</title>
              <path
                d="M5.8 21L7.4 14L2 9.2L9.2 8.6L12 2L14.8 8.6L22 9.2L18.8 12H18C17.3 12 16.6 12.1 15.9 12.4L18.1 10.5L13.7 10.1L12 6.1L10.3 10.1L5.9 10.5L9.2 13.4L8.2 17.7L12 15.4L12.5 15.7C12.3 16.2 12.1 16.8 12.1 17.3L5.8 21M17 14V17H14V19H17V22H19V19H22V17H19V14H17Z"
              />
            </svg>
          </template>
        </ProjectCard>
      </ProjectGrid>
    </section>

    <!-- Section des annonces -->
    <section class="announcements-section">
      <Announcements title="Announcements" :announcements="announcements" />
    </section>

    <!-- Section des tendances -->
    <section class="trending-section">
      <TrendingList title="Trending" :trends="trends" />
    </section>

    <!-- Section des utilisateurs -->
    <section class="users-section">
      <h2>User List</h2>
      <table class="user-table">
        <thead>
          <tr>
            <th>Name</th>
            <th>Email</th>
            <th>Role</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(user, index) in users" :key="index">
            <td>{{ user.name }}</td>
            <td>{{ user.email }}</td>
            <td>{{ user.role }}</td>
          </tr>
        </tbody>
      </table>
    </section>
  </div>
</template>

<style scoped>
.dashboard-container {
  padding: 24px;
  max-width: 1200px;
  margin: 0 auto;
}

.projects-section,
.announcements-section,
.trending-section,
.users-section {
  margin-bottom: 40px;
}

.user-table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 16px;
}

.user-table th,
.user-table td {
  padding: 12px;
  text-align: left;
  border-bottom: 1px solid #ddd;
}

.user-table th {
  background-color: #f4f4f4;
  font-weight: bold;
}
</style>
