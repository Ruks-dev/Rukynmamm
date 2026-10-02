<template>
  <section id="hero" class="hero">
    <div class="blob blob-1"></div>
    <div class="blob blob-2"></div>

    <div class="hero-inner">
      <span class="section-label">Hi, I'm</span>
      <h1>Ruqayya A Yusuf</h1>
      <h2 class="role">Final-Year Software Engineering Student</h2>
      <p class="tagline">
        I build  web applications — from open-banking dashboards to
        legal document systems — with a focus on clean interfaces and
        problems worth solving. Based in Abuja, Nigeria.
      </p>
      <div class="cta-row">
        <a href="#projects" class="btn btn-primary">View my work</a>
        <a href="#contact" class="btn btn-ghost">Get in touch</a>
      </div>
    </div>
  </section>
  
</template>

<script setup></script>

<style scoped>
.hero {
  position: relative;
  overflow: hidden;
  padding: 7rem 1.5rem 6rem;
}

.blob-1 {
  width: 420px;
  height: 420px;
  top: -160px;
  right: -120px;
  background: radial-gradient(circle at 30% 30%, var(--sage), var(--army-green) 75%);
  opacity: 0.25;
}
.blob-2 {
  width: 220px;
  height: 220px;
  bottom: -80px;
  right: 220px;
  background: radial-gradient(circle at 40% 40%, var(--mustard), var(--sand) 80%);
  opacity: 0.3;
}

.hero-inner {
  position: relative;
  z-index: 1;
  max-width: var(--max-width);
  margin: 0 auto;
}

h1 {
  font-size: clamp(3rem, 8vw, 5.5rem);
  font-weight: 600;
}

.role {
  font-family: var(--font-body);
  font-weight: 600;
  font-size: 1.25rem;
  color: var(--charcoal);
  margin-bottom: 1.25rem;
}

.tagline {
  font-size: 1.05rem;
  color: var(--warm-gray);
  margin-bottom: 2.25rem;
}

.cta-row {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

</style>