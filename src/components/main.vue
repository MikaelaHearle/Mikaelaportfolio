<template>
  <div class="page">
    <Header v-model:isMenuOpen="isMenuOpen" />
    <div v-if="isMenuOpen" class="overlay" @click="isMenuOpen = false" />
    <Aside
      v-if="isMenuOpen"
      id="site-aside"
      class="header-aside"
      @close="isMenuOpen = false"
    />
    <div id="main-content" class="main-template">
      <section id="about-me" aria-label="About me section">
        <About />
      </section>
      <section id="projects" aria-label="Projects section">
        <Projects />
      </section>
      <section id="contact" aria-label="Contact me form section">
        <Contact />
        <Footer />
      </section>
    </div>
  </div>
</template>

<script setup lang="ts">
import About from "./about.vue";
import Header from "./header.vue";
import Projects from "./projects.vue";
import Footer from "./footer.vue";
import Aside from "./aside.vue";
import { ref } from "vue";
import Contact from "./contact.vue";

const isMenuOpen = ref(false);
</script>

<style scoped>
.page {
  display: block;
}

.header-aside {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 100;
}

.overlay {
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.35);
  z-index: 5;
}

.main-template {
  position: relative;
  display: grid;
  grid-template-rows: 1fr;
  margin-top: 3rem;
  width: 100%;
  gap: 3rem;
}

@media (min-width: 768px) {
  .header-aside {
    width: 15rem;
  }
}

@media (min-width: 1440px) {
  .main-template {
    margin-top: 10rem;
    gap: 3rem;
  }
}
</style>
