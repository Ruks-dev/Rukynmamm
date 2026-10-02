<template>
  <footer class="footer">
    <div class="footer-inner">
      <span>© {{ year }} Rukynmamm. Built with caution.</span>
      <a href="#hero" class="back-top">Back to top ↑</a>
    </div>
  </footer>
</template>

<script>
const year = new Date().getFullYear()
</script>

<style>
.footer {
  background: var(--army-green-dark);
  color: var(--cream);
}
.footer-inner {
  max-width: var(--max-width);
  margin: 0 auto;
  padding: 1.75rem 1.5rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 0.75rem;
  font-size: 0.9rem;
}
.back-top {
  color: var(--cream);
  opacity: 0.8;
}
.back-top:hover { opacity: 1; }
</style>