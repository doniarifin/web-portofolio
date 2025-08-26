<template>
  <div class="mx-auto">
    <section id="about">
      <About />
    </section>
    <section id="experience">
      <Experience />
    </section>
    <section id="projects">
      <Project />
    </section>
    <section id="contact">
      <Contact />
    </section>
  </div>
</template>

<script setup>
import About from "./About.vue";
import Project from "./Projects.vue";
import Contact from "./Contact.vue";
import Experience from "./Experience.vue";
</script>
