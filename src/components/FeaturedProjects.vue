<template>
  <div class="projects-container">
    <!-- Heading -->
    <div class="heading">
      <h2 class="title">Featured Projects</h2>
      <p class="subtitle">Some of my recent work and contributions</p>
    </div>

    <!-- Project Cards Grid -->
    <div class="projects-grid">
      <div class="project-card" v-for="(project, index) in projects" :key="index" :style="{ background: project.gradient }" :class="{ disabled: project.disabled }">
        <div class="card-top">
          <div class="code-icon">&lt;/&gt;</div>
          <span class="status-badge" :class="{ live: project.status === 'Live', progress: project.status === 'In Progress' }">
            {{ project.status }}
          </span>
        </div>

        <div class="card-body">
          <h3 class="project-title">{{ project.title }}</h3>
          <p class="project-desc">{{ project.description }}</p>

          <div class="tech-tags">
            <span class="tag" v-for="tech in project.tech" :key="tech">{{ tech }}</span>
          </div>

          <div class="card-footer">
            <div class="stats">
              <span class="star">⭐ {{ project.stars }}</span>
              <span class="watchers">👥 {{ project.watchers }}</span>
            </div>
            <a :href="project.link" target="_blank" class="external-link">🔗</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const projects = ref([
  {
    title: "Travel Booking Platform",
    description: "Travel booking platform with Vue, Node.js and Vuetify.",
    tech: ["Vue.js", "Node.js", "Vuetify", "Bootstrap"],
    status: "In Progress",
    stars: 124,
    watchers: 32,
    link: "#",
    gradient: "linear-gradient(to bottom right, #6366f1, #ec4899)",
  },
  {
    title: "Task Management App",
    description: "Collaborative task management...",
    tech: ["Vue 3", "TypeScript", "Socket.io", "Pinia"],
    status: "In Progress",
    stars: 89,
    watchers: 21,
    link: "#",
    gradient: "linear-gradient(to bottom right, #10b981, #d1fae5)",
    disabled: true,
  },
  {
    title: "Design System",
    description: "Component library with Storybook...",
    tech: ["Vue.js", "Tailwind", "Figma"],
    status: "Live",
    stars: 156,
    watchers: 45,
    link: "#",
    gradient: "linear-gradient(to bottom right, #f97316, #ec4899)",
    disabled: true,
  },
]);
</script>

<style scoped>
.projects-container {
  padding: 40px 20px;
  width: 95%;
  margin: 0 auto;
  background: #0f172a;
  color: #f1f5f9;
  border-radius: 20px;
}

.heading {
  text-align: center;
  margin-bottom: 40px;
}

.title {
  font-size: 30px;
  font-weight: bold;
  color: #38bdf8;
}

.subtitle {
  font-size: 15px;
  color: #94a3b8;
}

.projects-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 24px;
  justify-content: center;
}

.project-card {
  border-radius: 12px;
  overflow: hidden;
  width: 400px;
  background: #1e293b;
  display: flex;
  flex-direction: column;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.5);
}

.card-top {
  position: relative;
  height: 180px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.code-icon {
  font-size: 40px;
  color: white;
}

.status-badge {
  position: absolute;
  top: 10px;
  right: 10px;
  padding: 4px 10px;
  border-radius: 999px;
  font-size: 12px;
  font-weight: 600;
  background-color: #0f172a;
  color: #fff;
  opacity: 0.9;
}

.status-badge.live {
  background-color: #10b981;
}

.status-badge.progress {
  background-color: #f59e0b;
}

.card-body {
  background: #1e293b;
  padding: 20px;
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.project-title {
  font-size: 18px;
  font-weight: 600;
}

.project-desc {
  font-size: 14px;
  color: #cbd5e1;
}

.tech-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.tag {
  font-size: 12px;
  background: #334155;
  color: #f1f5f9;
  padding: 4px 8px;
  border-radius: 6px;
}

.card-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 13px;
  margin-top: 10px;
}

.stats {
  display: flex;
  gap: 10px;
  color: #e0e7ff;
}

.external-link {
  font-size: 18px;
  text-decoration: none;
  color: #60a5fa;
}

.disabled {
  opacity: 0.4;
  filter: grayscale(80%);
  pointer-events: none;
}
</style>
