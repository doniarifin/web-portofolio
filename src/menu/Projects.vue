<template>
  <div class="py-32 pb-40">
    <div class="text-center mb-10">
      <h1 class="text-gray-300 font-bold">Projects</h1>
    </div>
    <div class="gap-4">
      <!-- <div>
        <hr />
      </div> -->
      <Project3 />
      <div>
        <hr />
      </div>
      <Project1 />
      <div>
        <hr />
      </div>
      <Project2 />
      <div>
        <hr />
      </div>
      <PersonalProject />
      <div>
        <hr />
      </div>
    </div>
    <div class="">
      <div
        class="hover:text-secondary hover:scale-125 transition duration-300 ease-in-out hover:text-shadow-[0_4px_8px_#d1d5db]"
      >
        <div class="grid mb-10 text-xl text-gray-300 text-center mt-6">
          <a
            class="hover:text-secondary hover:underline"
            href="https://github.com/doniarifin"
            target="_blank"
          >
            <p>Show more projects</p>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import PersonalProject from "../components/PersonalProject.vue";
import Project1 from "../components/Project1.vue";
import Project2 from "../components/Project2.vue";
import Project3 from "../components/Project3.vue";
</script>
