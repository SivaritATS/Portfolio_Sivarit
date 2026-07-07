<template>
  <div class="card">
    <div :class="['card-thumb', project.thumbClass]">{{ project.title.toUpperCase() }} — {{ project.id }}</div>
    <div class="card-body">
      <span class="tag">{{ project.tag }}</span>
      <h4>{{ project.title }}</h4>
      <p>{{ project.desc }}</p>
      <a class="link" :href="project.link" target="_blank">View on GitHub →</a>
    </div>
  </div>
</template>

<script setup>
defineProps({
  project: {
    type: Object,
    required: true
  }
});
</script>

<style scoped>
.card {
  background: var(--surface);
  border: 1px solid var(--line);
  border-radius: var(--radius);
  overflow: hidden;
  transition: .3s;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
}

.card:hover {
  transform: translateY(-6px);
  border-color: var(--accent);
  box-shadow: 0 10px 20px -2px rgba(0, 0, 0, 0.1);
}

.card-thumb {
  height: 150px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'JetBrains Mono';
  font-size: 0.75rem;
  color: #FFFFFF;
  letter-spacing: 1px;
}

.thumb-1 {
  background: linear-gradient(135deg, #4F46E5, #3730A3);
}

.thumb-2 {
  background: linear-gradient(135deg, #059669, #047857);
}

.thumb-3 {
  background: linear-gradient(135deg, #DB2777, #BE185D);
}

.thumb-4 {
  background: linear-gradient(135deg, #2563EB, #1D4ED8);
}

.thumb-5 {
  background: linear-gradient(135deg, #06B6D4, #0891B2);
}

.card-body {
  padding: 22px;
}

.tag {
  font-family: 'JetBrains Mono';
  font-size: 0.7rem;
  color: var(--accent);
  background: var(--accent-soft);
  border: 1px solid var(--accent-soft);
  padding: 3px 10px;
  border-radius: 999px;
}

.card-body h4 {
  margin: 12px 0 8px;
  font-size: 1.15rem;
}

.card-body p {
  color: var(--muted);
  font-size: 0.88rem;
  margin-bottom: 16px;
}

.card-body a.link {
  font-family: 'JetBrains Mono';
  font-size: 0.78rem;
  color: var(--accent);
}
</style>
