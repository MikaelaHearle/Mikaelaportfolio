<template>
  <header class="header">
    <img
      src="../assets/images/Header.svg"
      alt="Decorative background image"
      class="header-background"
      aria-hidden="true"
    />
    <ContentBlock>
      <nav aria-label="Navigation bar">
        <ul v-if="largeScreen" class="nav-list">
          <li><a href="#about-me">About me</a></li>
          <li><a href="#projects">Project</a></li>
          <li><a href="#contact">Contact me</a></li>
        </ul>

        <div v-else class="nav-list">
          <button 
            class="header-menu-button"
            :aria-expanded="isMenuOpen ? 'true' : 'false'"
            aria-controls="site-aside"
            aria-label="Open menu"
            @click="toggleMenu">
            <img src="../assets/images/menu.svg" alt="" aria-hidden="true" />
          </button>
        </div>
      </nav>
      <div class="header-content">
        <h1>Mikaela Andersson</h1>
        <p class="header-description">Front End Developer</p>
      </div>
    </ContentBlock>
  </header>
</template>

<script setup lang="ts">
import ContentBlock from "./templates/content-block.vue";
import { useMediaQuery } from "@vueuse/core";

const props = defineProps<{ isMenuOpen: boolean }>();
const emit = defineEmits<{
  (e: 'update:isMenuOpen', value: boolean): void;
}>();

const largeScreen = useMediaQuery("(min-width: 1024px)");

const toggleMenu = () => {
  emit('update:isMenuOpen', !props.isMenuOpen)
};
</script>

<style scoped>
.header {
  position: relative;
}

.header-background {
  background-repeat: no-repeat;
  background-size: contain;
  background-position: center;
  width: 100%;
  max-height: 40rem;
  position: absolute;
  z-index: -1;
  transform: rotate(180deg);
  transform-origin: center;
}

.nav-list {
  list-style-type: none;
  display: flex;
  justify-content: flex-end;
  gap: 2rem;
  padding: 0 1.5rem;
}

.nav-list a {
  display: inline-block;
  position: relative;
  font-family: "Chopin";
  font-size: 1.3rem;
  color: rgb(75, 65, 2);
  text-decoration: none;
}

.nav-list a::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: 1px;
  height: 1px;
  width: 0;
  background: rgb(75, 65, 2);
  transition: width 300ms ease;
}

.nav-list a:hover::after {
  width: 100%;
}

.header-menu-button {
  background: transparent;
  border: none;
  padding: 0;
  cursor: pointer;
}

.menu-button:focus {
  outline: 3px solid Highlight;
  outline-offset: 2px;
  border-radius: 4px;
}

.header-description {
  font-size: 1.3rem;
}

@media (min-width: 1440px) {
  .header-content {
    padding: 0rem;
  }

  .header-description {
    font-size: 1.5rem;
  }

  .nav-list a {
    font-size: 1.5rem;
  }
}
</style>
