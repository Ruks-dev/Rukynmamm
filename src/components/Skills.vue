<template>
  <section id="skills" class="section skills">
    <span class="section-label">Skills</span>
    <h2>What I work with</h2>

    <div class="skill-groups">
      <div class="skill-group" v-for="group in groups" :key="group.title">
        <h3>{{ group.title }}</h3>
        <div class="tags">
          <span class="tag" v-for="tag in group.items" :key="tag">{{ tag }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>

const groups = [
  {
    title: 'Frontend',
    items: ['HTML', 'CSS', 'JavaScript', 'Vue.js', 'React (learning)'],
  },
  {
    title: 'UI/UX Design',
    items: ['Figma', 'Canva', 'Sketch (learning)'],
  },
  {
    title: 'Tools & Workflow',
    items: ['Git & GitHub', 'Netlify'],
  },
]

</script>

<style scoped>
.skill-groups {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
  margin-top: 2.5rem;
}

.skill-group h3 {
  font-size: 1.05rem;
  color: var(--charcoal);
  font-weight: 700;
  font-family: var(--font-body);
  margin-bottom: 1rem;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.6rem;
}

.tag {
  background: var(--off-white);
  border: 1.5px solid var(--sand);
  color: var(--army-green-dark);
  padding: 0.45rem 1rem;
  border-radius: 999px;
  font-size: 0.88rem;
  font-weight: 500;
}

@media (max-width: 800px) {
  .skill-groups { grid-template-columns: 1fr; }
}
</style>