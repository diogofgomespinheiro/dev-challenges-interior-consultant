<script setup lang="ts"></script>

<template>
  <footer class="footer-container">
    <span
      >created by
      <a
        class="footer__link"
        href="https://github.com/diogofgomespinheiro"
        target="_blank"
        >diogofgomespinheiro</a
      >
      -
      <a class="footer__link" href="https://devchallenges.io" target="_blank"
        >devChallenges.io</a
      ></span
    >
  </footer>
</template>

<style>
.footer-container {
  color: var(--accent-text);
  font-weight: 500;
  font-size: 0.875rem;
  text-align: center;
  padding: 2.5rem 1.5rem;
}

.footer__link {
  font-weight: 700;
}

.footer__link:hover {
  text-decoration: underline;
}
</style>

<script lang="ts">
export default {
  name: 'CustomFooter'
};
</script>
