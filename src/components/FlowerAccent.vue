<template>
  <div class="flower-cluster" :style="{ '--fc-scale': scale }">
    <div class="flower" v-for="(f, i) in flowers" :key="i" :style="f.style">
      <span class="petal" v-for="n in 6" :key="n" :style="{ '--i': n, background: f.color }"></span>
      <span class="center"></span>
    </div>
    <span class="leaf" v-for="n in 3" :key="'leaf' + n" :style="{ '--i': n }"></span>
    <span class="dot" v-for="n in 6" :key="'dot' + n" :style="{ '--i': n }"></span>
  </div>
</template>

<script setup>
defineProps({
  scale: { type: Number, default: 1 },
})

const flowers = [
  { color: 'var(--mustard)', style: { top: '0%', left: '10%', '--size': '46px' } },
  { color: 'var(--burnt-orange)', style: { top: '20%', left: '38%', '--size': '34px' } },
  { color: 'var(--sage)', style: { top: '38%', left: '4%', '--size': '30px' } },
]
</script>

<style scoped>
.flower-cluster {
  position: relative;
  width: 180px;
  height: 160px;
  transform: scale(var(--fc-scale));
  transform-origin: top left;
  pointer-events: none;
}

.flower {
  position: absolute;
  width: var(--size);
  height: var(--size);
}

.petal {
  position: absolute;
  width: 55%;
  height: 55%;
  top: 0;
  left: 50%;
  border-radius: 100% 0 100% 0;
  transform-origin: 0% 100%;
  transform: rotate(calc(60deg * var(--i))) scale(0.95);
  opacity: 0.9;
}

.center {
  position: absolute;
  top: 42%;
  left: 42%;
  width: 16%;
  height: 16%;
  background: var(--charcoal);
  border-radius: 50%;
  z-index: 2;
}

.leaf {
  position: absolute;
  width: 26px;
  height: 14px;
  background: var(--army-green);
  opacity: 0.75;
  border-radius: 0 100% 0 100%;
  top: calc(40% + var(--i) * 22px);
  left: calc(2% + var(--i) * 14px);
  transform: rotate(calc(-20deg * var(--i)));
}

.dot {
  position: absolute;
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: var(--sand);
  opacity: 0.7;
  top: calc(10% + var(--i) * 9px);
  right: calc(4% + var(--i) * 6px);
}
</style>