<template>
  <section id="experience" class="section experience">
    <span class="section-label">Experience</span>
    <h2>Where I've applied this</h2>

    <ol class="timeline">
      <li v-for="item in items" :key="item.title">
        <div class="dot"></div>
        <div class="content">
          <span class="period">{{ item.period }}</span>
          <h3>{{ item.title }}</h3>
          <p>{{ item.description }}</p>
        </div>
      </li>
    </ol>
  </section>
</template>

<script setup>

const items = [
  {
    period: 'Present',
    title: 'Building ECMS & R-FinView',
    description: 'Designing and building web applications end to end — from UI to database — as final-year portfolio projects.',
  },
  {
    period: 'Ongoing',
    title: 'Final-Year Software Engineering Coursework',
    description: 'Applying coursework in software engineering and computer science directly to shipped, working applications rather than isolated assignments.',
  },
]
</script>

<style scoped>
.timeline {
  list-style: none;
  margin: 2.5rem 0 0;
  padding: 0;
  border-left: 2px solid var(--sand);
}

.timeline li {
  position: relative;
  padding: 0 0 2.25rem 2rem;
}
.timeline li:last-child { padding-bottom: 0; }

.dot {
  position: absolute;
  left: -7px;
  top: 4px;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: var(--army-green);
  border: 2px solid var(--off-white);
}

.period {
  font-size: 0.8rem;
  font-weight: 600;
  color: var(--burnt-orange);
  text-transform: uppercase;
  letter-spacing: 0.04em;
}

.content h3 {
  font-size: 1.15rem;
  margin: 0.3rem 0 0.4rem;
}
.content p {
  margin: 0;
  color: var(--warm-gray);
  font-size: 0.95rem;
}
</style>
