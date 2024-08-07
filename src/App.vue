<script setup>
import HelloWorld from './components/HelloWorld.vue'
import HomeView from './components/HomeView.vue'
import Profile from './components/Profile.vue'
import Works from './components/Works.vue'
import Project2 from './components/Project2.vue'
import ContactMe from './components/ContactMe.vue'
</script>

<template>
  <div class="mb-4">
    <HomeView />
    <section id="about">
      <Profile />
    </section>
    <section id="works">
      <Works />
      <Project2 />
    </section>
    <section id="contact">
      <ContactMe />
    </section>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
