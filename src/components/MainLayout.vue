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
  padding: 20px;
}
</style>

<script lang="ts">
export default {
  name: 'MainLayout'
};
</script>
