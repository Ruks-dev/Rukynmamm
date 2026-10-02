<template>
  <section id="Certification" class="section education">
    <span class="section-label">Certifications</span>
    <h2>Academic background</h2>

    <div class="edu-card">
      <div>
        <h3>Philomath University</h3>
        <p class="program">Computer Science / Software Engineering — Final Year</p>
      </div>
    </div>
<br><br>
     <h2>Online Certification</h2>

    <div class="edu-card">
      <div>
        <h3>FreeCodeCamp</h3>
        <p class="program">Responsive Web Design Certification</p>
      </div>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
.edu-card {
  margin-top: 2.5rem;
  background: var(--cream);
  border-radius: var(--radius-lg);
  padding: 2rem 2.25rem;
  display: flex;
  align-items: center;
  gap: 1.5rem;
}

h3 {
  margin-bottom: 0.3rem;
}

.program {
  margin: 0;
  color: var(--charcoal);
  font-weight: 500;
}
</style>
