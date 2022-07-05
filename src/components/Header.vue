<script setup lang="ts"></script>

<template>
  <header class="header-container">
    <nav class="navbar">
      <a class="logo" href="/">This Interior</a>
      <div
        class="navbar-toggler"
        :class="{ hidden: !isMobile }"
        @click="toogleNav"
      >
        <img src="/assets/menu-icon.svg" alt="Menu Icon" :height="30" />
      </div>
      <div class="navbar-menu" :class="{ mobile: isMobile, hidden: !isOpen }">
        <div
          class="navbar__close-button"
          :class="{ hidden: !isOpen }"
          @click="toogleNav"
        >
          <img src="/assets/close-button.svg" alt="Menu Icon" :height="30" />
        </div>
        <ul
          class="navbar-menu__list"
          :class="{ mobile: isMobile, hidden: !isOpen }"
        >
          <li
            class="navbar-menu__item"
            :class="{ active: isActiveItem('home') }"
            @click="() => selectItem('home')"
          >
            <a class="navbar-menu__link" href="#">Home</a>
          </li>
          <li
            class="navbar-menu__item"
            :class="{ active: isActiveItem('collection') }"
            @click="() => selectItem('collection')"
          >
            <a class="navbar-menu__link" href="#">Collection</a>
          </li>
          <li
            class="navbar-menu__item"
            :class="{ active: isActiveItem('about') }"
            @click="() => selectItem('about')"
          >
            <a class="navbar-menu__link" href="#">About</a>
          </li>
          <li
            class="navbar-menu__item"
            :class="{ active: isActiveItem('contact') }"
            @click="() => selectItem('contact')"
          >
            <a class="navbar-menu__link" href="#">Contact</a>
          </li>
        </ul>
      </div>
    </nav>
  </header>
</template>

<style>
.header-container {
  width: 100%;
  padding: 1.25rem 0.75rem;
}

.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}

.navbar-toggler.hidden,
.navbar-menu.mobile.hidden,
.navbar__close-button.hidden {
  display: none;
}

.navbar-menu {
  font: 500 1.125rem 'Montserrat', sans-serif;
}

.navbar-menu.mobile {
  display: flex;
  flex-direction: column;
  position: absolute;
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  background-color: var(--background-color);
  z-index: 100;
}

.navbar-menu__list {
  display: flex;
  gap: 3.75rem;
  list-style: none;
}

.navbar-menu__list.mobile {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  flex: 1;
}

.navbar-toggler {
  cursor: pointer;
}

.navbar__close-button {
  align-self: flex-end;
  margin-top: 1.25rem;
  margin-right: 0.75rem;
  cursor: pointer;
}

.navbar-menu__item.active {
  font-weight: 700;
  border-bottom: 2px solid #fff;
}

.logo {
  padding: 0.5rem;
  border: 1px solid #fff;
  cursor: pointer;
  font: 400 0.875rem 'Crimson Pro', sans-serif;
  text-transform: uppercase;
}

@media screen and (min-width: 768px) {
  .header-container {
    padding: 2.5rem 4.75rem;
  }
}
</style>

<script lang="ts">
type NavItems = 'home' | 'collection' | 'about' | 'contact';
interface Data {
  selectedItem: NavItems;
  isOpen: boolean;
  isMobile: boolean;
}

export default {
  name: 'CustomHeader',
  data(): Data {
    return {
      selectedItem: 'home',
      isOpen: false,
      isMobile: false
    };
  },
  created() {
    window.addEventListener('resize', this.verifyScreen);
    this.verifyScreen();
  },
  methods: {
    toogleNav(): void {
      if (this.isMobile) {
        this.isOpen = !this.isOpen;
      }
    },
    selectItem(item: NavItems): void {
      this.selectedItem = item;
      this.toogleNav();
    },
    isActiveItem(item: NavItems): boolean {
      return this.selectedItem === item;
    },
    verifyScreen() {
      if (window.innerWidth <= 767) {
        this.isMobile = true;
        return;
      }
      this.isMobile = false;
      this.isOpen = false;
    }
  }
};
</script>
