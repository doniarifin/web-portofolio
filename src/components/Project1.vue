<template>
  <div class="w-[80%] h-[100%] justify-center mx-[auto] h-px bg-gray-300 border-0 dark:bg-gray-700 opacity-100"></div>
  <div ref="fadeElement" class="opacity-0 invisible">
    <h1 class="w-[80%] h-[100%] mx-[auto] lg:text-6xl text-justify md:text-6xl sm:text-6xl text-4xl text-gray-300 font-bold pt-16 mb-4">Projects</h1>
    <div class="w-[80%] h-[100%] justify-center mx-[auto] hover:scale-105 transition duration-300 ease-in-out pb-10">
      <div class="lg:flex mx-auto">
        <div class="w-[auto] md:w-[auto] md:item-center opacity-100 mt-10">
          <div class="rounded">
            <div class="p-3">
              <img src="../assets/works1.png" alt="" class="rounded shadow-[0px_0px_13px_0px_rgb(209_213_219)]">
            </div>
          </div>
        </div>
        <div class="w-[auto] md:w-[auto] md:item-center rounded">
          <div class="grid lg:mx-12 text-xl text-gray-300 text-justify mt-10">
            <h1 class="text-[#FBFBFB] text-2xl font-bold">
              Customizing the SAP Business User Interface for Petrosea Career Site
            </h1>
          </div>
          <div class="grid lg:mx-12 text-xl text-gray-300 text-justify mt-6">
            <p>
              Worked on enhancing the SAP Business User Interface for Petrosea's career site to support their recruitment marketing strategies, aimed at building a strong employer brand and engaging potential candidates effectively.
            </p>
          </div>
          <div class="grid mb-10 lg:mx-12 text-xl text-gray-300 text-justify mt-6">
            <p class="text-[#54B4D3] font-bold">
              HTML, CSS, JavaScript.
            </p>
          </div>
          <div class="mb-10 lg:mx-12 text-xl mt-10">
            <a href="https://career.petrosea.com/" 
              class="
                text-[#313550]
                bg-gray-300
                hover:scale-105
                transition
                duration-300
                ease-in-out
                font-medium 
                rounded-xl
                text-sm
                inline-flex
                items-center
                justify-center
                px-4
                py-2
              "
            >
              Website 
              <mdicon name="arrow-right" width="20" class="ml-2" />
            </a>
          </div>
        </div>
        <div class="w-[auto] md:w-[auto] md:item-center bg-[#242738] hidden "></div>
      </div>
    </div>
  </div>
</template>
<script setup>
import { ref, onMounted } from 'vue';

const fadeElement = ref(null);

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          fadeElement.value.classList.remove('opacity-0', 'invisible');
          fadeElement.value.classList.add('fadeInRight-animation');
          observer.unobserve(fadeElement.value);
        }
      });
    },
    {
      threshold: 0.1
    }
  );
  if (fadeElement.value) {
    observer.observe(fadeElement.value);
  }
});
</script>