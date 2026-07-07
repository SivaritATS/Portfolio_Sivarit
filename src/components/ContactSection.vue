<template>
  <section id="contact">
    <div class="wrap">
      <div class="contact-container">
        <span class="eyebrow">Say Hello</span>
        <h1>Let's know each other.</h1>
        <p class="subtitle">
          I'm grateful to have you here. If you have any questions or want to work together, feel free to reach out.
        </p>

        <div class="contact-cards">
          <div class="contact-card-item">
            <div class="icon">@</div>
            <h3>Email</h3>
            <span>sivarit.kit@gmail.com</span>
          </div>

          <div class="contact-card-item">
            <div class="icon">📍</div>
            <h3>Location</h3>
            <span>Pathum Thani, Thailand</span>
          </div>

          <div class="contact-card-item">
            <div class="icon">☎</div>
            <h3>Phone</h3>
            <span>+66 62 549 6450</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
// Static contact section
</script>

<style scoped>
.contact-container {
  text-align: center;
  max-width: 800px;
  margin: 0 auto;
  padding: 40px 0;
}

.contact-container h1 {
  font-size: clamp(2rem, 5vw, 2.8rem);
  margin: 15px 0;
}

.subtitle {
  color: var(--muted);
  max-width: 500px;
  margin: 0 auto 50px;
  font-size: 1rem;
  line-height: 1.6;
}

.contact-cards {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
}

.contact-card-item {
  background: var(--surface);
  border: 1px solid var(--line);
  border-radius: var(--radius);
  padding: 36px 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  transition: 0.3s ease;
}

.contact-card-item:hover {
  transform: translateY(-6px);
  border-color: var(--accent);
  box-shadow: 0 10px 20px -2px rgba(0, 0, 0, 0.05);
}

.contact-card-item .icon {
  width: 48px;
  height: 48px;
  border-radius: 12px;
  background: var(--accent-soft);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.25rem;
  color: var(--accent);
  margin-bottom: 20px;
}

.contact-card-item h3 {
  font-family: 'JetBrains Mono';
  font-size: 0.8rem;
  color: var(--muted);
  letter-spacing: 0.05em;
  text-transform: uppercase;
  margin-bottom: 10px;
}

.contact-card-item span {
  font-size: 0.95rem;
  color: var(--ink);
  word-break: break-all;
}

@media (max-width: 768px) {
  .contact-cards {
    grid-template-columns: 1fr;
    gap: 16px;
  }
}
</style>
