<script setup lang="ts">
import MainLayout from './components/MainLayout.vue';
import Card from './components/Card.vue';
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
</script>

<template>
  <Header />
  <MainLayout>
    <div class="main-content-wrapper">
      <div class="description-container">
        <h1>Modern interior</h1>
        <h3>
          A full-Service residentials & commercial interior design and staging
          company offering professional organizing & eco-services.
        </h3>
        <a href="/">Read more<span class="arrow">→</span></a>
      </div>
      <div class="banner-container">
        <img class="banner" src="/assets/banner.png" alt="Living Room" />
        <Card
          title="Designed in 2020 by <br> Aliza Webber"
          :user="{
            name: 'Aliza Webber',
            profession: 'Interior designer',
            profileImgSrc: '/assets/profile.png'
          }"
        />
      </div>
    </div>
  </MainLayout>
  <Footer />
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
  --accent-text: #a9a9a9;
}

html,
body,
#app {
  min-height: 100vh;
  height: 100%;
  display: flex;
  flex-direction: column;
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
    font-size: 75%;
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

.main-content-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;

  margin: 0 auto;
  max-width: 1440px;
  gap: 2.5rem;
  padding-bottom: 3.75rem;
}

.description-container > h1 {
  font: 500 3rem 'Lora', sans-serif;
}

.description-container > h3 {
  margin: 2.5rem 0;
  font: 400 1.5rem 'Montserrat', sans-serif;
}

.description-container > a {
  font: 700 1.125rem 'Montserrat', sans-serif;
}

.description-container .arrow {
  margin-left: 0.875rem;
  font-size: 1.5rem;
}

.banner-container {
  position: relative;
  max-width: 880px;
  margin: 0 auto;
}

.card {
  position: absolute;
  right: 2%;
  bottom: 0;
  transform: translateY(50%);

  width: 60%;
  max-width: 410px;
}

.banner {
  width: 100%;
}

@media screen and (min-width: 1200px) {
  .main-content-wrapper {
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    padding-bottom: 0;
  }

  .description-container,
  .banner-container {
    max-width: 48%;
  }
}
</style>
