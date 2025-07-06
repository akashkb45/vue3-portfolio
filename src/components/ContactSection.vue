<template>
  <div class="contact-section">
    <!-- Top Stats -->
    <div class="stats-grid">
      <div v-for="stat in stats" :key="stat.label" :style="{ background: stat.bg }" class="stat-card">
        <h3>{{ stat.value }}</h3>
        <p>{{ stat.label }}</p>
      </div>
    </div>

    <!-- Call to Action -->
    <div class="cta">
      <h2 class="cta-title">Let's Work Together</h2>
      <p class="cta-desc">
        Ready to bring your ideas to life? Let's discuss your next project and create something
        <span class="highlight">amazing</span>.
      </p>

      <div class="cta-buttons">
        <a href="mailto:akashkb45@gmail.com" class="btn primary" target="_blank"> ✉️ Send Email </a>
        <a href="https://wa.me/919074145470" class="btn outline" target="_blank"> 💬 Chat on WhatsApp </a>
      </div>

      <div class="social-icons">
        <a href="#" target="_blank">🐱</a>
        <a href="#" target="_blank">💼</a>
        <a href="mailto:akashkb45@gmail.com" target="_blank">✉️</a>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const stats = ref([
  { value: "50+", label: "Projects Completed", bg: "linear-gradient(to right, #a78bfa, #e0e7ff)" },
  { value: "3+", label: "Years Experience", bg: "linear-gradient(to right, #6ee7b7, #d1fae5)" },
  { value: "25+", label: "Happy Clients", bg: "linear-gradient(to right, #fdba74, #fff7ed)" },
  { value: "100%", label: "Client Satisfaction", bg: "linear-gradient(to right, #f472b6, #fce7f3)" },
]);
</script>

<style scoped>
.contact-section {
  padding: 60px 20px;
  background: #0f172a;
  color: #f1f5f9;
  text-align: center;
  border-radius: 20px;
}

.stats-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 20px;
  margin-bottom: 40px;
}

.stat-card {
  padding: 20px 30px;
  border-radius: 16px;
  min-width: 200px;
  color: #111827;
  font-weight: 600;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
}

.stat-card h3 {
  font-size: 24px;
  margin-bottom: 6px;
}

.stat-card p {
  font-size: 14px;
  color: #374151;
}

.cta-title {
  font-size: 28px;
  color: #d946ef;
  font-weight: bold;
}

.cta-desc {
  margin-top: 10px;
  font-size: 15px;
  color: #cbd5e1;
}

.cta-desc .highlight {
  color: #a78bfa;
  font-weight: 600;
}

.cta-buttons {
  margin-top: 24px;
  display: flex;
  justify-content: center;
  gap: 16px;
  flex-wrap: wrap;
}

.btn {
  padding: 10px 20px;
  font-weight: 600;
  border-radius: 8px;
  text-decoration: none;
  display: inline-block;
  transition: 0.3s ease;
}

.primary {
  background: linear-gradient(to right, #a855f7, #ec4899);
  color: white;
  box-shadow: 0 4px 10px rgba(236, 72, 153, 0.3);
}

.outline {
  border: 2px solid #a855f7;
  color: #a855f7;
}

.primary:hover {
  opacity: 0.9;
}

.outline:hover {
  background: #a855f7;
  color: white;
}

.social-icons {
  margin-top: 30px;
  font-size: 22px;
  display: flex;
  justify-content: center;
  gap: 20px;
}

.social-icons a {
  color: #f1f5f9;
  transition: 0.3s ease;
}

.social-icons a:hover {
  color: #a78bfa;
}
</style>
