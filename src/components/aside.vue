<template>
  <aside
    class="aside"
    role="dialog"
    aria-modal="true"
    aria-labelledby="aside-title"
  >
    <div class="aside-inner">
      <header>
        <h2 id="aside-title" class="visually-hidden">Menu</h2>
        <button class="aside-close-button" aria-label="close menu" @click="emit('close')">
          <img
            src="../assets/images/close.svg"
            alt="Close menu"
            aria-hidden="true"
          />
        </button>
      </header>
      <nav class="aside-nav" aria-label="Mobile navigation">
          <ul class="nav-list">
          <li><a href="#about-me" @click="emit('close')">About me</a></li>
          <li><a href="#projects" @click="emit('close')">Project</a></li>
          <li><a href="#contact" @click="emit('close')">Contact me</a></li>
          </ul>
      </nav>
    </div>
  </aside>
</template>

<script setup lang="ts">
const emit = defineEmits(['close']);
</script>

<style scoped>
.aside {
  background-color: #f5f5f5;
  padding: 1rem;
  z-index: 100;
}

.aside-close-button {
  background: none;
  border: none;
  position: absolute;
  top: 1rem;
  right: 1rem;
}

.nav-list {
  list-style-type: none;
  display: block;
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
</style>
