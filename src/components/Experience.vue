<template>
  <div class="lg:h-screen">
    <div class="pb-10 text-gray-300 font-bold">
      <h1>Experience</h1>
    </div>
    <div ref="fadeElement" class="opacity-0 invisible">
      <div class="hover:scale-105 transition duration-300 ease-in-out">
        <div
          class="lg:text-justify bg-thirdly rounded-full text-center p-14 shadow-lg shadow-accent grid gap-2"
        >
          <div class="grid gap-1">
            <h1 class="text-2xl font-bold">
              Software Developer | PT Kano Teknologi Indonesia
            </h1>
            <h2 class="text-xl">May 2022 - Dec 2024</h2>
          </div>
          <div class="py-2">
            <p>
              Developed and maintained web applications for various clients
              using Golang for backend services and Vue.js with Tailwind CSS for
              frontend interfaces. Integrated MongoDB for data management and
              ensured code quality, performance, and scalability. Collaborated
              closely with internal teams and clients to deliver reliable and
              maintainable software solutions aligned with business goals.
            </p>
          </div>
          <div class="lg:flex gap-2 text-center grid">
            <div v-for="skill in data.skill">
              <div class="bg-secondary p-2 rounded-full shadow-xl">
                {{ skill }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
import { ref, onMounted, reactive } from "vue";

const fadeElement = ref(null);

const data = reactive({
  skill: ["Golang", "Vuejs", "MongoDB", "SQL Server"],
});

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          fadeElement.value.classList.remove("opacity-0", "invisible");
          fadeElement.value.classList.add("fadeInRight-animation");
          observer.unobserve(fadeElement.value);
        }
      });
    },
    {
      threshold: 0.1,
    }
  );
  if (fadeElement.value) {
    observer.observe(fadeElement.value);
  }
});
</script>
