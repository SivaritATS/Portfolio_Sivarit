<template>
  <footer>
    <div class="wrap">
      <p>© 2026 Sivarit ATS. All rights reserved.</p>
    </div>
  </footer>
</template>

<script setup>
</script>

<style scoped>
footer {
  border-top: 1px solid var(--line);
  padding: 34px 0;
  margin-top: 40px;
}

footer .wrap {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 16px;
}

footer p {
  color: var(--muted);
  font-size: 0.82rem;
  font-family: 'JetBrains Mono';
}
</style>
