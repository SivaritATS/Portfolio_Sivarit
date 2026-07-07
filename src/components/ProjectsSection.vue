<template>
  <section id="projects">
    <div class="wrap">
      <span class="eyebrow">My Projects</span>
      <div class="section-head">
        <h2>All Projects</h2>
      </div>
      <div class="filter-row">
        <button :class="['filter-btn', { active: activeFilter === 'all' }]" @click="activeFilter = 'all'">
          All
        </button>
        <button :class="['filter-btn', { active: activeFilter === 'Next JS' }]" @click="activeFilter = 'Next JS'">
          Next JS
        </button>
        <button :class="['filter-btn', { active: activeFilter === 'Vue JS' }]" @click="activeFilter = 'Vue JS'">
          Vue JS
        </button>
        <button :class="['filter-btn', { active: activeFilter === 'Flutter' }]" @click="activeFilter = 'Flutter'">
          Flutter
        </button>
      </div>

      <div class="proj-grid">
        <ProjectCard v-for="project in filteredProjects" :key="project.id" :project="project" />
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue';
import ProjectCard from './ProjectCard.vue';

const props = defineProps({
  projects: {
    type: Array,
    required: true
  }
});

const activeFilter = ref('all');

const filteredProjects = computed(() => {
  if (activeFilter.value === 'all') return props.projects;
  return props.projects.filter(project => project.tag === activeFilter.value);
});
</script>

<style scoped>
.filter-row {
  display: flex;
  gap: 10px;
  margin-bottom: 30px;
}

.filter-row button {
  font-family: 'JetBrains Mono';
  font-size: 0.78rem;
  padding: 8px 16px;
  border-radius: 999px;
  border: 1px solid var(--line);
  background: transparent;
  color: var(--muted);
  cursor: pointer;
}

.filter-row button.active {
  background: var(--accent);
  color: #FFFFFF;
  border-color: var(--accent);
}
</style>
