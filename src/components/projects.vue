<template>
  <ContentBlock>
    <template #title>
      <h2>Projects</h2>
    </template>
      <div class="projects-description">
        <p>Here are a few of my projects</p>
      </div>
    <div class="projects-grid">
      <Card
        title="Arctic Paper customer shop"
        description="Maintenance of existing solutions"
        link="https://www.arcticpaper.com/"
        :image="arctic"
        imageAlt="Screenshot of Arctic Paper website"
      />
      <Card
        title="Olsson Parts"
        description="Maintenance and accessibility improvements"
        link="https://www.olssonparts.com/se/sv/?gad_source=1&gad_campaignid=23334035995&gbraid=0AAAAADt2NLKq494w8EYLQceZbxdQ5mJO_&gclid=CjwKCAiA95fLBhBPEiwATXUsxNOlhEvtbRWdFkScFfhOfRxAVxLdUWW2hTiQp9DoUAcOI85iG5t3ihoC4wwQAvD_BwE"
        :image="olsson"
        imageAlt="Screenshot of Olsson Parts website"
      />
      <Card
        title="Aba Skol"
        description="Maintenance & improved accessibility"
        link="https://abaskol.se/"
        :image="abaskol"
        imageAlt="Screenshot of Aba Skol website"
      />
      <Card
        title="Trioworld"
        description="Maintenance and UI improvements"
        link="https://www.trioworld.com/?utm_source=google&utm_medium=cpc&utm_term=trioworld&campaign_id=23370712013&ad_group_id=188967343094&ad_id=788571872610&match_type=b&target=kwd-363320852845&gad_source=1&gad_campaignid=23370712013&gbraid=0AAAAA97N1XYFZ6WiS8puiauS7PHerHKan&gclid=CjwKCAiA95fLBhBPEiwATXUsxAjU7eCKDLLlruzlwUFycBql2NjVGT8m6j5c5oOvchtl-TynEGzvHBoCEagQAvD_BwE"
        :image="trioworld"
        imageAlt="Screenshot of Trioworld website"
      />
      <Card
        title="Norept customer portal"
        description="Development of a new customer portal"
        link="https://norept.se/"
        :image="norept"
        imageAlt="Screenshot of Norept website"
      />
      <Card
        title="Vattenfall internal intranet"
        description="Development of an internal intranet"
        link="https://www.vattenfall.se/"
        :image="vattenfall"
        imageAlt="Screenshot of Vattenfall website"
      />
    </div>
  </ContentBlock>
</template>

<script setup lang="ts">
import Card from "./templates/card.vue";
import ContentBlock from "./templates/content-block.vue";
import arctic from '../assets/images/arcticpaper.png';
import olsson from '../assets/images/olssonparts.png';
import abaskol from '../assets/images/abaskol.png';
import trioworld from '../assets/images/trioworld.png';
import norept from '../assets/images/norept.png';
import vattenfall from '../assets/images/vattenfall.png';
</script>

<style scoped>
.projects-description {
  margin-bottom: 2rem;
}

.projects-grid {
  display: grid;
  gap: 1.25rem;
  grid-auto-rows: 1fr;
  width: 100%;
  max-width: 70rem;
  margin-inline: auto;

  /* desktop: 3 kolumner */
  grid-template-columns: repeat(3, 1fr);
}

/* tablet & down: 1 kolumn */
@media (max-width: 1024px) {
  .projects-grid {
    grid-template-columns: 1fr;
  }
}
</style>
