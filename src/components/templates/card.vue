<template>
<a :href="props.link || '/project/1'" target="_blank" class="card" :aria-label="ariaLabel" tabindex="0">
    <div class="card-media" v-if="hasMedia">
      <slot name="image">
        <img
          v-if="props.image"
          :src="props.image"
          :alt="props.imageAlt || props.title || ''"
          loading="lazy"
        />
      </slot>
    </div>

    <div class="card-content">
      <slot>
        <h3 class="card-title">{{ props.title }}</h3>
        <p class="card-desc">{{ props.description }}</p>
      </slot>
    </div>
  </a>
</template>

<script setup lang="ts">
import { computed } from "vue";

const props = defineProps<{
  title?: string;
  description?: string;
  link?: string;
  image?: string;
  imageAlt?: string;
}>();

const ariaLabel = computed(() =>
  props.title ? `Open project: ${props.title}` : "Open project"
);

const hasMedia = computed(() => Boolean(props.image));
</script>

<style scoped>
.card {
  display: block;
  height: 100%;
  border: 1px solid rgb(190, 159, 50);
  border-radius: 8px;
  overflow: hidden;
  background: #fff;
  text-decoration: none;
  color: inherit;
  transition: transform .18s ease, box-shadow .18s ease;
}

.card:focus {
  outline: 3px solid Highlight;
  outline-offset: 2px;
  border-radius: 8px;
}

.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 24px rgba(0,0,0,0.12);
}
.card-content {
  padding: 1rem;
}

.card-media img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.card-content {
  padding: 1rem;
  display: flex;
  flex-direction: column;
  gap: .5rem;
  height: calc(100% - 10rem);
  box-sizing: border-box;
}

.card-title {
  margin: 0;
  font-size: 1.05rem;
}

.card-desc {
  margin: 0;
  color: #444;
  font-size: .95rem;
  flex: 1 0 auto;
}
</style>
