<template>
  <section id="home">
    <div class="wrap">
      <HeroSection @contact-click="$emit('navigate', 'contact')" />

      <AboutSection :skills-list="skillsList" />

      <div style="margin-top:100px;">
        <div class="section-head">
          <div>
            <span class="eyebrow">My Projects</span>
            <h2 style="margin-top:10px;">A few things I've built</h2>
          </div>
          <button class="btn btn-ghost" @click="$emit('navigate', 'projects')">All Projects →</button>
        </div>
        <div class="proj-grid">
          <ProjectCard 
            v-for="project in projects.slice(0, 3)" 
            :key="project.id" 
            :project="project" 
          />
        </div>
      </div>

      <div class="cta-band">
        <h2>Ready to learn and create better work.</h2>
        <button class="btn btn-primary" @click="$emit('navigate', 'contact')">Contact Me →</button>
      </div>
    </div>
  </section>
</template>

<script setup>
import HeroSection from './HeroSection.vue';
import AboutSection from './AboutSection.vue';
import ProjectCard from './ProjectCard.vue';

defineProps({
  projects: {
    type: Array,
    required: true
  },
  skillsList: {
    type: Array,
    required: true
  }
});

defineEmits(['navigate']);
</script>

<style scoped>
/* CTA */
.cta-band {
  margin-top: 70px;
  padding: 50px 40px;
  text-align: center;
  border-radius: var(--radius);
  background: var(--surface);
  border: 1px solid var(--line);
}

.cta-band h2 {
  font-size: 1.9rem;
  margin-bottom: 20px;
}
</style>
