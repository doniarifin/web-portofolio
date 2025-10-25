<template>
  <div class="py-32 pb-40">
    <div class="text-center">
      <h1 class="text-gray-300 font-bold">Projects</h1>
    </div>
    <Project3 />
    <Project1 />
    <Project2 />
    <PersonalProject />
  </div>
</template>

<script setup>
import PersonalProject from "../components/PersonalProject.vue";
import Project1 from "../components/Project1.vue";
import Project2 from "../components/Project2.vue";
import Project3 from "../components/Project3.vue";
</script>
