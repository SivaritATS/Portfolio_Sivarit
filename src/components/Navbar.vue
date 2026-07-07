<template>
  <nav>
    <div class="wrap">
      <div class="brand">My<span>Portfolio</span></div>
      <div class="nav-links">
        <button :class="['nav-btn', { active: currentPage === 'home' }]" @click="$emit('navigate', 'home')">
          Home
        </button>
        <button :class="['nav-btn', { active: currentPage === 'projects' }]" @click="$emit('navigate', 'projects')">
          Projects
        </button>
        <button :class="['nav-btn', { active: currentPage === 'contact' }]" @click="$emit('navigate', 'contact')">
          Contact
        </button>
      </div>
      <button class="theme-toggle" @click="$emit('toggle-theme')" aria-label="Toggle Theme">
        <svg v-if="theme === 'light'" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-moon"><path d="M12 3a6 6 0 0 0 9 9 9 9 0 1 1-9-9Z"/></svg>
        <svg v-else xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-sun"><circle cx="12" cy="12" r="4"/><path d="M12 2v2"/><path d="M12 20v2"/><path d="m4.93 4.93 1.41 1.41"/><path d="m17.66 17.66 1.41 1.41"/><path d="M2 12h2"/><path d="M20 12h2"/><path d="m6.34 17.66-1.41 1.41"/><path d="m19.07 4.93-1.41 1.41"/></svg>
      </button>
    </div>
  </nav>
</template>

<script setup>
defineProps({
  currentPage: {
    type: String,
    required: true
  },
  theme: {
    type: String,
    required: true
  }
});

defineEmits(['navigate', 'toggle-theme']);
</script>

<style scoped>
nav {
  position: sticky;
  top: 0;
  z-index: 50;
  background: var(--bg);
  opacity: 0.95;
  backdrop-filter: blur(10px);
  border-bottom: 1px solid var(--line);
  transition: background-color 0.3s ease, border-color 0.3s ease;
}

nav .wrap {
  display: flex;
  align-items: center;
  gap: 20px;
  padding: 16px 28px;
}

.brand {
  font-family: 'Space Grotesk';
  font-weight: 700;
  font-size: 1.8rem;
  letter-spacing: 0.02em;
  margin-right: auto;
}

.brand span {
  color: var(--accent);
}

.nav-links {
  display: flex;
  gap: 6px;
  background: var(--surface);
  padding: 5px;
  border-radius: 999px;
  border: 1px solid var(--line);
}

.nav-links button {
  font-family: 'Inter';
  font-size: 0.85rem;
  padding: 8px 16px;
  border-radius: 999px;
  background: transparent;
  border: none;
  color: var(--muted);
  cursor: pointer;
  transition: .25s;
}

.nav-links button.active {
  background: var(--surface-2);
  color: var(--ink);
  font-weight: 500;
}

.nav-links button:hover:not(.active) {
  color: var(--ink);
  background: var(--surface-2);
}

.theme-toggle {
  background: var(--surface-2);
  border: 1px solid var(--line);
  color: var(--ink);
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: 0.25s;
}

.theme-toggle:hover {
  background: var(--accent-soft);
  color: var(--accent);
  border-color: var(--accent);
}
</style>
