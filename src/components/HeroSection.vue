<template>
  <div class="hero">
    <div>
      <span class="eyebrow">Junior Full Stack Developer</span>
      <h1>Hello, my name is<br><span class="accent">Sivarit.</span></h1>
      <p class="lead">I build clean, functional interfaces with React and Next.js, and power them with robust backends.
        Always eager for the next technical challenge.</p>
      <div class="btn-row">
        <button class="btn btn-primary" @click="$emit('contact-click')">Contact Me →</button>
        <a class="btn btn-ghost"
          href="https://drive.google.com/file/d/1BzCBUe4vZ7r6CxEmuNT6EReRRRuDWkKe/view?usp=sharing"
          target="_blank">Resume</a>
      </div>
      <div class="socials">
        <a href="https://github.com/SivaritATS" title="GitHub" target="_blank" rel="noopener noreferrer">
          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"
            stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
            class="lucide lucide-github">
            <path
              d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4" />
            <path d="M9 18c-4.51 2-5-2-7-2" />
          </svg>
        </a>
        <a href="https://www.instagram.com/poompoomzzz/" title="Instagram" target="_blank" rel="noopener noreferrer">
          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none"
            stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"
            class="lucide lucide-instagram">
            <rect width="20" height="20" x="2" y="2" rx="5" ry="5" />
            <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z" />
            <line x1="17.5" x2="17.51" y1="6.5" y2="6.5" />
          </svg>
        </a>
      </div>
    </div>
    <div class="avatar-wrap">
      <div class="ring">
        <svg viewBox="0 0 200 200">
          <defs>
            <path id="circlePath" d="M100,100 m-85,0 a85,85 0 1,1 170,0 a85,85 0 1,1 -170,0" />
          </defs>

        </svg>
      </div>
      <!--<div class="dot"></div>-->
      <div class="avatar-core">
        <img src="../assets/me.jpg" alt="Sivarit" />
      </div>
    </div>
  </div>
</template>

<script setup>
defineEmits(['contact-click']);
</script>

<style scoped>
.hero {
  display: grid;
  grid-template-columns: 1.1fr 0.9fr;
  gap: 40px;
  align-items: center;
}

.hero h1 {
  font-size: clamp(2.2rem, 5vw, 3.4rem);
  line-height: 1.08;
  margin-bottom: 18px;
}

.hero h1 .accent {
  color: var(--accent);
}

.hero p.lead {
  color: var(--muted);
  font-size: 1.05rem;
  max-width: 460px;
  margin-bottom: 32px;
}

.btn-row {
  display: flex;
  gap: 14px;
  flex-wrap: wrap;
  margin-bottom: 36px;
}

.avatar-wrap {
  position: relative;
  width: 390px;
  height: 390px;
  margin: 0 auto;
}

.ring {
  position: absolute;
  inset: 0;
  border-radius: 50%;
  border: 1.5px dashed var(--accent-soft);
  animation: spin 30s linear infinite;
  box-shadow: 0 0 40px var(--accent-soft);
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }

  to {
    transform: rotate(360deg);
  }
}

.ring svg {
  width: 100%;
  height: 100%;
}

.ring text {
  font-family: 'JetBrains Mono';
  font-size: 11.5px;
  fill: var(--accent);
  letter-spacing: 2px;
}

.avatar-core {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 350px;
  height: 350px;
  border-radius: 50%;
  background: var(--surface-2);
  border: 2px solid var(--line);
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Space Grotesk';
  font-weight: 700;
  font-size: 3rem;
  color: var(--accent);
  box-shadow: 0 0 60px var(--accent-soft);
  overflow: hidden;
}

.avatar-core img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 50%;
}


.dot {
  position: absolute;
  width: 14px;
  height: 14px;
  background: var(--accent);
  border-radius: 50%;
  top: 8px;
  left: 50%;
  box-shadow: 0 0 12px var(--accent-soft);
}

@media (max-width: 760px) {
  .hero {
    grid-template-columns: 1fr;
  }
}
</style>
