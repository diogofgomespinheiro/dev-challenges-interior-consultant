<script setup lang="ts"></script>

<template>
  <main class="main-container">
    <slot />
  </main>
</template>

<style>
.main-container {
  display: flex;
  flex-direction: column;
  justify-content: center;

  height: 100%;
  padding: 20px;
}

@media screen and (min-width: 768px) {
  .main-container {
    flex-direction: row;
    align-items: center;

    padding: 40px 60px;
  }
}
</style>

<script>
export default {
  name: 'MainLayout'
};
</script>
