<script setup>
import { ref } from "vue";
import ContactSection from "./ContactSection.vue";
import FeaturedProjects from "./FeaturedProjects.vue";
import TechnicalSkills from "./TechnicalSkills.vue";

const tab = ref("");
const skills = ref(null);
const projects = ref(null);
const contacts = ref(null);

const scroll = (sectionName) => {
  const sectionRefs = {
    skills,
    projects,
    contacts,
  };
  const section = sectionRefs[sectionName];
  const domElement = section?.value?.$el || section?.value;

  if (domElement && domElement.scrollIntoView) {
    domElement.scrollIntoView({ behavior: "smooth" });
    tab.value = sectionName === "skills" ? "about" : sectionName;
  } else {
    console.warn("Section not found:", sectionName);
  }
};
</script>

<template>
  <div class="profile-dashboard">
    <div class="dashboard-container">
      <div class="inner-block">
        <header class="profile-header">
          <div class="logo">AKASH K B</div>
          <nav class="navigation">
            <span :class="{ active: tab === 'projects' }" @click="scroll('projects')">Projects</span>
            <span :class="{ active: tab === 'about' }" @click="scroll('skills')">About</span>
            <span :class="{ active: tab === 'contact' }" @click="scroll('contacts')">Contact</span>
          </nav>
          <div class="socials">
            <a href="https://github.com/akashkb45" target="_blank" aria-label="GitHub">
              <i class="fab fa-github"></i>
            </a>
            <a href="https://linkedin.com/in/akash-k-b-744169283" target="_blank" aria-label="LinkedIn">
              <i class="fab fa-linkedin-in"></i>
            </a>
            <a href="https://instagram.com/_ak_a__sh_" target="_blank" aria-label="Instagram">
              <i class="fab fa-instagram"></i>
            </a>
            <a href="https://x.com/akashkb_45" target="_blank" aria-label="Twitter">
              <i class="fab fa-x-twitter"></i>
            </a>
            <a href="https://facebook.com/akash.aachi.1" target="_blank" aria-label="Facebook">
              <i class="fab fa-facebook"></i>
            </a>
          </div>
        </header>

        <div class="profile-content">
          <h1>
            My name is Akash K B, <br />
            I work as a Front-end Developer
          </h1>
          <p>I build modern, responsive, and user-friendly websites with a focus on clean design and efficient code.</p>
        </div>

        <TechnicalSkills ref="skills" />
        <FeaturedProjects ref="projects" />
        <ContactSection ref="contacts" />
      </div>
    </div>
  </div>
</template>

<style scoped>
html {
  scroll-behavior: smooth;
}

section {
  scroll-margin-top: 80px;
}

.profile-dashboard .dashboard-container {
  padding: 50px;
}

.profile-dashboard .dashboard-container .inner-block {
  display: flex;
  flex-direction: column;
  row-gap: 40px;
}

.profile-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.profile-header .logo {
  font-size: 2rem;
  font-weight: 700;
  color: #ffffff;
}

.profile-header .navigation {
  display: flex;
  justify-content: center;
  gap: 20px;
}

.profile-header .navigation span {
  margin: 0 15px;
  font-size: 1.2rem;
  cursor: pointer;
  text-align: center;
  position: relative;
  padding-bottom: 5px;
}

.profile-header .navigation span::after {
  content: "";
  position: absolute;
  width: 0;
  height: 2px;
  bottom: 0;
  left: 0;
  background: #00f9ff;
  transition: width 0.3s ease;
}

.profile-header .navigation span:hover::after {
  width: 100%;
}

.profile-header .navigation span:hover {
  color: #00f9ff;
}

.profile-header .navigation .selected {
  color: #00f9ff;
}

.profile-header .navigation .selected::after {
  content: "";
  position: absolute;
  width: 100%;
  height: 2px;
  bottom: 0;
  left: 0;
  background: #00f9ff;
  transition: width 0.3s ease;
}

.profile-header .socials {
  display: flex;
  gap: 15px;
}

.socials a {
  color: #ffffff;
  font-size: 1.2rem;
  transition: color 0.3s;
}

.profile-header .socials a:hover {
  color: #00f9ff;
}

.profile-header .profile-pages {
  display: flex;
  gap: 25px;
}

.profile-header .profile-pages i {
  font-size: 1.4rem;
  margin: 0 5px;
  cursor: pointer;
}

.profile-header .profile-pages i:hover {
  color: #00f9ff;
}

.profile-content {
  margin: 30px 0;
  height: 400px;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.profile-content h1 {
  font-size: 4rem;
  text-align: center;
  color: #fff;
  animation: fadeInSlideUp 2s ease-out;
}

.profile-content p {
  margin: 0;
  font-size: 1.8rem;
  animation: fadeInSlideUp 3s ease-out;
}

@keyframes fadeInSlideUp {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.project-container .project-header {
  width: 100%;
  position: relative;
}

.project-container .project-header h4 {
  font-size: 2.5rem;
  padding: 15px 0;
  color: #00f9ff;
  position: relative;
}

.project-container .project-header h4::after {
  content: "";
  position: absolute;
  height: 2px;
  bottom: 0;
  left: 0;
  background: #00f9ff;
  animation: slideInBorder 1s ease forwards;
  width: 100%;
}

.project-container .project-content {
  display: flex;
  gap: 15px;
}

.project-container .project-content .project-card {
  padding: 10px;
  background-color: rgba(0, 0, 0, 0.229);
  background-blend-mode: overlay;
  background-size: contain;
  width: 300px;
  border-radius: 20px;
  height: 460px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  filter: grayscale(100%);
  transition: 0.5s ease-in-out;
}

.project-container .project-content .project-card h1 {
  text-transform: uppercase;
  font-size: 2rem;
}

.project-container .project-content .project-card:hover {
  transform: scale(1.1);
  background-color: rgba(0, 0, 0, 0.7);
  filter: grayscale(0%);
}

@keyframes slideInBorder {
  0% {
    width: 0;
  }
  100% {
    width: 100%;
  }
}
</style>
