<template>
  <section id="skills" class="section skills">
    <span class="section-label">Skills</span>
    <h2>What I work with</h2>

    <div class="skills-layout">
      <div class="skills-left">
        <p>
          A breakdown of where my hands-on time actually goes — from building
          interfaces in Vue to shaping the data layer underneath them.
        </p>

        <div class="tags">
          <span class="tag" v-for="s in skills" :key="s.label">{{
            s.label
          }}</span>
        </div>

        <FlowerBranch class="corner-flower" />
      </div>

      <div class="skills-right">
        <div class="pie-chart" :style="{ background: pieGradient }">
          <div class="pie-hole"></div>
        </div>

        <ul class="legend">
          <li v-for="s in skills" :key="s.label">
            <span class="swatch" :style="{ background: s.color }"></span>
            <span class="legend-label">{{ s.label }}</span>
            <span class="legend-pct">{{ s.percent }}%</span>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script setup>
import { computed } from "vue";
import FlowerAccent from "./FlowerAccent.vue";


const skills = [
 { label: "HTML/CSS", percent: 37, color: "var(--mustard)" },
  { label: "Vue.js", percent: 22, color: "var(--army-green)" },
 { label: "UI/UX Design", percent: 19, color: "var(--warm-gray)" },
 { label: "React (learning)", percent: 13, color: "var(--sand)" },
  { label: "JavaScript", percent: 8, color: "var(--burnt-orange)" },
  { label: "Node.js / Backend(learning)", percent: 2, color: "var(--sage)" },
  
];

const pieGradient = computed(() => {
  let cursor = 0;
  const stops = skills.map((s) => {
    const start = cursor;
    cursor += s.percent;
    return `${s.color} ${start}% ${cursor}%`;
  });
  return `conic-gradient(${stops.join(", ")})`;
});
</script>

<style scoped>
.skills-layout {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  align-items: center;
  margin-top: 2.5rem;
}

.skills-left {
  position: relative;
  min-height: 240px;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.6rem;
  margin: 1.5rem 0 3rem;
}

.tag {
  background: var(--off-white);
  border: 1.5px solid var(--sand);
  color: var(--army-green-dark);
  padding: 0.45rem 1rem;
  border-radius: 999px;
  font-size: 0.85rem;
  font-weight: 500;
}

.corner-flower {
  position: absolute;
  bottom: -20px;
  left: -10px;
}

.skills-right {
  display: flex;
  align-items: center;
  gap: 2rem;
  flex-wrap: wrap;
  justify-content: center;
}

.pie-chart {
  width: 220px;
  height: 220px;
  border-radius: 50%;
  position: relative;
  flex-shrink: 0;
  box-shadow: var(--shadow-card);
}

.pie-hole {
  position: absolute;
  inset: 30%;
  background: var(--off-white);
  border-radius: 50%;
}

.legend {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: 0.85rem;
}
.legend li {
  display: flex;
  align-items: center;
  gap: 0.65rem;
  font-size: 0.92rem;
}
.swatch {
  width: 12px;
  height: 12px;
  border-radius: 3px;
  flex-shrink: 0;
}
.legend-label {
  color: var(--charcoal);
  font-weight: 500;
}
.legend-pct {
  color: var(--warm-gray);
  margin-left: auto;
  font-variant-numeric: tabular-nums;
}

@media (max-width: 800px) {
  .skills-layout {
    grid-template-columns: 1fr;
  }
  .corner-flower {
    display: none;
  }
}
</style>
