<script setup lang="ts">
import HeroComponent from "./sections/HeroSection.vue";
import FooterSection from "./sections/FooterSection.vue";
import AboutSection from "./sections/AboutSection.vue";
import ProjectsSection from "./sections/ProjectsSection.vue";
import SkillsSection from "./sections/SkillsSection.vue";
import ExperienceSection from "./sections/ExperienceSection.vue";
import DiplomaSection from "./sections/DiplomaSection.vue";
import NavComponent from "../components/NavComponent.vue";
</script>

<template>
  <header>
    <NavComponent />
  </header>
  <main>
    <HeroComponent />
    <AboutSection />
    <ProjectsSection />
    <SkillsSection />
    <ExperienceSection />
    <DiplomaSection />
  </main>
  <FooterSection />
</template>

<style scoped></style>
