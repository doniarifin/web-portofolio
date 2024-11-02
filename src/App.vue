<script setup>
import HomeView from './components/HomeView.vue'
import Profile from './components/Profile.vue'
import Project1 from './components/Project1.vue'
import Project2 from './components/Project2.vue'
import ContactMe from './components/ContactMe.vue'
</script>

<template>
  <div class="">
    <HomeView />
    <section id="about">
      <Profile />
    </section>
    <section id="projects">
      <Project1 />
      <Project2 />
    </section>
    <section id="contact">
      <ContactMe />
    </section>
  </div>
  
  <!-- Footer -->
  <footer class="footer">
    <div class="justify-end">
      <a href="https://github.com/doniarifin"
          class="
            hover:scale-105
            transition
            duration-300
            ease-in-out
            font-medium 
            rounded-xl
            inline-flex
            items-center
            justify-center
          "
        >Dhoni
        <mdicon name="github" width="20" class="ml-2" />
      </a>
    </div>
  </footer>
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
.footer {
  text-align: center;
  font-weight: 300;
  padding: 1rem;
  background-color: var(--dark);
  color: whitesmoke;
  /* position: fixed; */
  /* width: 100%; */
  bottom: 0;
}
</style>
