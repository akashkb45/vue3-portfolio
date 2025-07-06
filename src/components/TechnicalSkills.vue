<template>
  <div class="technical-skills-container dark">
    <!-- Heading -->
    <div class="heading-section">
      <h2 class="main-heading">Technical Skills</h2>
      <p class="sub-heading">Technologies and tools I work with daily</p>
    </div>

    <!-- Skill Cards -->
    <div class="skills-grid">
      <div class="skill-card" v-for="skill in skills" :key="skill.name" :style="{ borderTop: '4px solid ' + skill.color }">
        <div class="card-header">
          <div class="icon" :style="{ backgroundColor: skill.color + '33' }">
            <i :class="skill.icon"></i>
          </div>
          <h3>{{ skill.name }}</h3>
        </div>

        <div class="progress-section">
          <p class="label">Proficiency</p>
          <div class="progress-bar">
            <div class="progress-fill" :style="{ width: skill.percentage + '%', backgroundColor: skill.color }"></div>
          </div>
          <span class="percentage">{{ skill.percentage }}%</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const skills = ref([
  { name: "Vue.js", percentage: 95, color: "#42b883", icon: "fab fa-vuejs" },
  { name: "Vuex", percentage: 70, color: "#10b981", icon: "fas fa-database" },
  { name: "JavaScript", percentage: 80, color: "#facc15", icon: "fab fa-js-square" },
  { name: "Tailwind CSS", percentage: 90, color: "#06b6d4", icon: "fas fa-paint-brush" },
  { name: "REST APIs", percentage: 85, color: "#f97316", icon: "fas fa-plug" },
  { name: "SCSS / CSS3", percentage: 90, color: "#d946ef", icon: "fab fa-css3-alt" },
  { name: "Git & GitHub", percentage: 70, color: "#f43f5e", icon: "fab fa-git-alt" },
]);
</script>

<style scoped>
.technical-skills-container {
  padding: 40px 20px;
  background: #0f172a; /* slate-900 */
  border-radius: 20px;
  width: 95%;
  margin: 0 auto;
  text-align: center;
  color: #e2e8f0; /* slate-200 */
}

.heading-section {
  margin-bottom: 30px;
}

.main-heading {
  font-size: 32px;
  font-weight: bold;
  color: #c084fc; /* violet-400 */
}

.sub-heading {
  font-size: 15px;
  color: #94a3b8; /* slate-400 */
  margin-top: 6px;
}

.skills-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}

.skill-card {
  background: #1e293b; /* slate-800 */
  border-radius: 12px;
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.4);
  padding: 20px;
  width: 280px;
  transition: transform 0.2s;
}

.skill-card:hover {
  transform: translateY(-4px);
}

.card-header {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 16px;
}

.card-header h3 {
  font-size: 18px;
  font-weight: 600;
  margin: 0;
  color: #f1f5f9; /* slate-100 */
}

.icon {
  width: 40px;
  height: 40px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #fff;
  font-size: 18px;
}

.progress-section .label {
  font-size: 14px;
  margin-bottom: 6px;
  color: #cbd5e1; /* slate-300 */
  text-align: left;
}

.progress-bar {
  background: #334155; /* slate-700 */
  height: 8px;
  border-radius: 4px;
  overflow: hidden;
}

.progress-fill {
  height: 100%;
  transition: width 0.4s ease;
}

.percentage {
  margin-top: 8px;
  font-size: 13px;
  color: #cbd5e1; /* slate-300 */
  text-align: right;
  display: block;
}
</style>
