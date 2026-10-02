<template>
  <header class="navbar" :class="{ scrolled }">
    <div class="navbar-inner">
      <a href="#hero" class="logo">Ruks<span>.Dev</span></a>

      <nav class="links" :class="{ open }">
        <a v-for="link in links" :key="link.href" :href="link.href" @click="open = false">
          {{ link.label }}
        </a>
      </nav>

      <button class="toggle" @click="open = !open" :aria-expanded="open" aria-label="Toggle menu">
        <span></span><span></span><span></span>
      </button>
    </div>
  </header>
</template>

<script>
import { ref, onMounted, onUnmounted } from 'vue'

const open = ref(false)
const scrolled = ref(false)

const links = [
  { label: 'About', href: '#about' },
  { label: 'Skills', href: '#skills' },
  { label: 'Projects', href: '#projects' },
  { label: 'Experience', href: '#experience' },
  { label: 'Education', href: '#education' },
  { label: 'Contact', href: '#contact' },
]

function onScroll() {
  scrolled.value = window.scrollY > 24
}

onMounted(() => window.addEventListener('scroll', onScroll))
onUnmounted(() => window.removeEventListener('scroll', onScroll))
</script>

<style scoped>
.navbar {
  position: sticky;
  top: 0;
  z-index: 50;
  background: rgba(250, 249, 246, 0.85);
  backdrop-filter: blur(8px);
  border-bottom: 1px solid transparent;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}
.navbar.scrolled {
  border-color: rgba(75, 83, 32, 0.12);
  box-shadow: 0 4px 20px rgba(43, 45, 42, 0.05);
}

.navbar-inner {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: 1.1rem 1.5rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo {
  font-family: var(--font-display);
  font-weight: 600;
  font-size: 1.3rem;
  color: var(--army-green-dark);
}
.logo span { color: var(--burnt-orange); }

.links {
  display: flex;
  gap: 2rem;
}
.links a {
  font-size: 0.95rem;
  font-weight: 500;
  color: var(--charcoal);
}
.links a:hover { color: var(--army-green); }

.toggle {
  display: none;
  flex-direction: column;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 4px;
}
.toggle span {
  width: 22px;
  height: 2px;
  background: var(--army-green-dark);
  border-radius: 2px;
}

@media (max-width: 720px) {
  .toggle { display: flex; }
  .links {
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    flex-direction: column;
    background: var(--off-white);
    padding: 1.5rem;
    gap: 1.25rem;
    display: none;
    border-bottom: 1px solid rgba(75, 83, 32, 0.12);
  }
  .links.open { display: flex; }
}
</style>