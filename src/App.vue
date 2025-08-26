<script setup>
import Navbar from "./components/Navbar.vue";
import Footer from "./menu/Footer.vue";
import MainSection from "./menu/MainSection.vue";
</script>

<template>
  <div class="wrapper">
    <header class="header-top w-full">
      <div class="mx-auto">
        <Navbar />
      </div>
    </header>

    <!-- Main content -->
    <div class="mx-auto max-w-7xl w-full">
      <MainSection class="mainsection w-full text-[#F9FAFB]" />
    </div>
    <!-- Footer -->
    <div class="w-full pb-40 footer-bottom">
      <Footer class="bg-gray-900 h-24 text-center" />
    </div>
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
.wrapper {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  flex: 1;
}

.header-top {
  top: 0;
  left: 0;
  position: fixed;
  width: 100%;
  z-index: 999;
}
.mainsection {
  /* max-width: 80rem; */
  flex: 1;
}
.footer-bottom {
  bottom: 0;
  left: 0;
  /* position: fixed; */
  width: 100vw;
  background-color: #111827;
  height: 6rem;
  /* display: flex; */
}
</style>
