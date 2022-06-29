<script setup lang="ts">
import MainLayout from './components/MainLayout.vue';
</script>

<template>
  <MainLayout>Test</MainLayout>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

:root {
  --background-color: #181719;
  --primary-text: #ffffff;
  --secondary-text: #828282;
}

html,
body,
#app {
  min-height: 100vh;
  height: 100%;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

@media (max-width: 1080px) {
  html {
    font-size: 93.75%;
  }
}

@media (max-width: 720px) {
  html {
    font-size: 87.5%;
  }
}

body {
  background: var(--background-color);
  color: var(--primary-text);
}

body,
input,
textarea,
select,
button {
  font: 400 1rem 'Montserrat', sans-serif;
}

button {
  cursor: pointer;
}

a {
  color: inherit;
  text-decoration: none;
}
</style>
