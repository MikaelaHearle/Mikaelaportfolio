<template>
  <ContentBlock>
    <template #title>
      <h2>About Me</h2>
    </template>
    <div class="about-me__content">
        <p>
          I’m a frontend developer with a passion for clear communication, smart
          workflows, and creating digital experiences that feel effortless for
          users. I love bringing structure to fast-moving environments, supporting
          teams, and turning ideas into well-crafted results. Outside of work, I’m
          all about long distance running, cozy moments with my toddler and my
          very opinionated cat, and the tv show Married at First Sight Australia. In short: I’m curious, driven, and happiest when I get to
          combine people, creativity, and technology to make things better.
          If you want to know more, download my resume here, in <a :href="resume" target="_blank" class="about-me__link">english</a> or <a :href="cv" target="_blank" class="about-me__link">swedish</a>.
        </p>
        <img src="../assets/images/mikaela.png" alt="Image of Mikaela" class="about-me__image" />
    </div>
  </ContentBlock>
</template>

<script setup lang="ts">
import ContentBlock from "./templates/content-block.vue";
import resume from '../assets/images/MikaelaHearleENG.pdf';
import cv from '../assets/images/MikaelaHearle.pdf';
</script>

<style scoped>
.about-me__content {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 2rem;
  max-width: 100vw;
  box-sizing: border-box;
  align-items: center;
  justify-items: center;
}

@media (max-width: 768px) {
  .about-me__content {
    grid-template-columns: 1fr;
  }
}

.about-me__content > * {
  min-width: 0;
}

.about-me__content img {
  display: block;
  height: auto;
  width: auto;
  object-fit: cover;
  max-width: 100%;
  max-height: 17rem;
}

.about-me__image {
  border: solid 8px rgb(190, 159, 50);
  border-radius: 50%;
}

.about-me__link {
  text-decoration: underline;
  color: rgb(190, 159, 50);
}
</style>
