<template>
  <main class="main-container">
    <slot />
  </main>
</template>

<style>
.main-container {
  display: flex;
  align-items: center;
  justify-content: center;
  flex: 1;
  padding: 0 0.75rem;
}

@media screen and (min-width: 768px) {
  .main-container {
    padding: 0 4.75rem;
  }
}
</style>

<script lang="ts">
export default {
  name: 'MainLayout'
};
</script>
