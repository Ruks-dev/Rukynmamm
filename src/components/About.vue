<template>
   <section id="about" class="section about">
    <div class="about-grid">
      <div>
        <span class="section-label">About</span>
        <h2>A bit about me</h2>
        <p>
          I'm a final-year Computer Science / Software Engineering student at
          Philomath University, building a frontend that
          solve real problems — from tracking finances across banks to
          digitizing legal paperwork. I care about interfaces that are easy
          to use and code that's easy to maintain.
        </p>
        <p>
          Outside of coursework, I deploy  my own projects — frontend and getting them ready.
        </p>
      </div>

      <div class="facts">
        <div class="fact" v-for="f in facts" :key="f.label">
          <span class="fact-label">{{ f.label }}</span>
          <span class="fact-value">{{ f.value }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const facts = [
  { label: 'Based in', value: 'Abuja, Nigeria' },
  { label: 'Studying at', value: 'Philomath University' },
  { label: 'Program', value: 'Computer Science / Software Engineering' },
  { label: 'GitHub', value: '@Ruks-dev' },
]
</script>

<style scoped>
.about-grid {
  display: grid;
  grid-template-columns: 1.4fr 1fr;
  gap: 3.5rem;
  align-items: start;
}

.facts {
  background: var(--cream);
  border-radius: var(--radius-lg);
  padding: 2rem;
  display: flex;
  flex-direction: column;
  gap: 1.25rem;
}

.fact {
  display: flex;
  flex-direction: column;
  gap: 0.15rem;
  border-bottom: 1px solid rgba(75, 83, 32, 0.15);
  padding-bottom: 1rem;
}
.fact:last-child { border-bottom: none; padding-bottom: 0; }

.fact-label {
  font-size: 0.8rem;
  text-transform: uppercase;
  letter-spacing: 0.04em;
  color: var(--warm-gray);
}
.fact-value {
  font-family: var(--font-display);
  font-weight: 500;
  font-size: 1.1rem;
  color: var(--army-green-dark);
}

@media (max-width: 800px) {
  .about-grid { grid-template-columns: 1fr; }
}
</style>