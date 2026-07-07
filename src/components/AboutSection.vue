<template>
  <div style="margin-top:100px;">
    <span class="eyebrow">About Me</span>
    <div class="about-grid">
      <div class="tab-col">
        <button :class="['about-tab', { active: activeAboutTab === 'personal' }]" @click="activeAboutTab = 'personal'">
          Personal Info
        </button>
        <button :class="['about-tab', { active: activeAboutTab === 'education' }]"
          @click="activeAboutTab = 'education'">
          Education
        </button>
        <button :class="['about-tab', { active: activeAboutTab === 'skills' }]" @click="activeAboutTab = 'skills'">
          Skills
        </button>
      </div>
      <div class="info-card">
        <div v-show="activeAboutTab === 'personal'" class="tab-panel">
          <h3>Nice to meet you, I'm Sivarit</h3>
          <p class="sub">You can get to know me better through the info below.</p>
          <div class="info-list">
            <div><span>NAME</span><span>Sivarit Atsawasapphayakit</span></div>
            <div><span>LOCATION</span><span>Pathum Thani, Thailand</span></div>
            <div><span>BORN</span><span>11 May</span></div>
            <div><span>LANGUAGES</span><span>Thai — English</span></div>
            <div><span>EMAIL</span><span>sivarit.kit@gmail.com</span></div>
          </div>
        </div>
        <div v-show="activeAboutTab === 'education'" class="tab-panel">
          <h3>Education</h3>
          <p class="sub">Where I've studied and trained.</p>
          <div class="edu-item">
            <div class="yr">2023 — 2026</div>
            <h4>B.Sc. in Computer Science / IT</h4>
            <p style="color:var(--muted); font-size:0.9rem;">Focused on full-stack web application development and
              robust software engineering fundamentals.</p>
          </div>
          <div class="edu-item">
            <div class="yr">Ongoing</div>
            <h4>Self-taught: React, Next.js, Vue.js</h4>
            <p style="color:var(--muted); font-size:0.9rem;">I am constantly developing my skills in web application
              development, mobile app development, and software engineering fundamentals.</p>
          </div>
        </div>
        <div v-show="activeAboutTab === 'skills'" class="tab-panel">
          <h3>Skills</h3>
          <p class="sub">Tools and technologies I work with.</p>
          <div class="skills-grid">
            <span class="pill" v-for="skill in skillsList" :key="skill">{{ skill }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

defineProps({
  skillsList: {
    type: Array,
    default: () => ['HTML5', 'Vue.js', 'JavaScript', 'React', 'Next.js', 'Docker', 'Tailwind CSS', 'Git & GitHub', 'Figma', 'TypeScript', 'Node.js']
  }
});

const activeAboutTab = ref('personal');
</script>

<style scoped>
.about-grid {
  display: grid;
  grid-template-columns: 220px 1fr;
  gap: 40px;
  margin-top: 20px;
}

.tab-col button {
  display: block;
  width: 100%;
  text-align: left;
  padding: 14px 18px;
  margin-bottom: 8px;
  background: transparent;
  border: 1px solid var(--line);
  border-radius: 12px;
  color: var(--muted);
  font-family: 'JetBrains Mono';
  font-size: 0.85rem;
  cursor: pointer;
  transition: .2s;
}

.tab-col button.active {
  background: var(--accent-soft);
  color: var(--accent);
  border-color: var(--accent);
}

.info-card {
  background: var(--surface);
  border: 1px solid var(--line);
  border-radius: var(--radius);
  padding: 36px;
}

.info-card h3 {
  font-size: 1.5rem;
  margin-bottom: 8px;
}

.info-card p.sub {
  color: var(--muted);
  margin-bottom: 26px;
}

.info-list div {
  display: flex;
  justify-content: space-between;
  padding: 12px 0;
  border-bottom: 1px solid var(--line);
  font-size: 0.95rem;
}

.info-list div span:first-child {
  color: var(--muted);
  font-family: 'JetBrains Mono';
  font-size: 0.8rem;
}

.skills-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.pill {
  font-family: 'JetBrains Mono';
  font-size: 0.8rem;
  padding: 9px 16px;
  background: var(--surface-2);
  border: 1px solid var(--line);
  border-radius: 999px;
  color: var(--ink);
}

.edu-item {
  margin-bottom: 22px;
}

.edu-item .yr {
  color: var(--accent);
  font-family: 'JetBrains Mono';
  font-size: 0.78rem;
}

@media (max-width: 760px) {
  .about-grid {
    grid-template-columns: 1fr;
  }

  .tab-col {
    display: flex;
    gap: 8px;
    overflow-x: auto;
  }

  .tab-col button {
    white-space: nowrap;
    margin-bottom: 0;
  }
}
</style>
