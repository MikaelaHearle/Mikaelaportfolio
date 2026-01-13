<template>
    <ContentBlock>
        <template #title>
            <h2>Contact Me</h2>
        </template>
        <div class="contact-me__content">
            <a href="mailto:mikaelahearle@gmail.com" target="_blank" class="contact-me__contact">
                <img src="../assets/images/mail.svg" alt="Email icon" aria-hidden="true" />
                <p>Email</p>
            </a>
            <a href="https://www.linkedin.com/in/mikaelahearle/" target="_blank" class="contact-me__contact">
                <img src="../assets/images/linkedin.svg" class="contact-me__content-icon" alt="Linkedin icon" aria-hidden="true" />
                <p>LinkedIn</p>
            </a>
            <a href="https://github.com/mikaelahearle" target="_blank" class="contact-me__contact">
                <img src="../assets/images/github.svg" class="contact-me__content-icon" alt="Github icon" aria-hidden="true" />
                <p>Github</p>
            </a>
        </div>
    </ContentBlock>
</template>

<script setup lang="ts">
import ContentBlock from "./templates/content-block.vue";
</script>

<style scoped>
.contact-me__content {
display: flex;
gap: 2rem;
justify-content: flex-start;
}

.contact-me__contact {
display: flex;
flex-direction: column;
align-items: center;
text-decoration: none;
}

.contact-me__content-icon {
width: 1.5rem;
height: 1.5rem;
}
</style>