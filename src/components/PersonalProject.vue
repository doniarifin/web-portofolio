<template>
  <div>
    <h1 class="text-4xl font-bold text-textcolor pt-20">Personal Project</h1>
  </div>
  <div ref="fadeElement" class="opacity-0 invisible">
    <div
      class="justify-center mx-[auto] hover:scale-105 transition duration-300 ease-in-out pb-10"
    >
      <div class="lg:flex grid mx-auto p-4 lg:p-2 gap-4 mx-auto">
        <div
          class="w-[auto] md:w-[auto] max-w-lg md:item-center opacity-100 mt-10"
        >
          <div class="rounded">
            <div
              class="p-3 cursor-pointer"
              @click="openImage('/images/cvbuilder.png')"
            >
              <img
                src="/images/cvbuilder.png"
                alt=""
                class="rounded shadow-[0px_0px_13px_0px_rgb(209_213_219)]"
              />
            </div>
          </div>
        </div>
        <div class="w-[auto] md:w-[auto] md:item-center rounded">
          <div class="grid text-gray-300 text-justify mt-10">
            <h1 class="text-white text-xl font-bold">CV Builder/Generator</h1>
          </div>
          <div class="grid text-gray-300 text-justify mt-6">
            <p>
              An application for creating CVs instantly and downloading them as
              PDF.
            </p>
          </div>
          <div class="grid mb-10 text-xl text-gray-300 text-justify mt-6">
            <p class="text-secondary font-bold">Vuejs, Tailwind CSS.</p>
          </div>
          <div class="mb-10 lg:mx-12 text-xl mt-10">
            <a
              href="https://doniarifin.github.io/vue-cvgenerator/"
              target="_blank"
              class="text-white bg-secondary hover:scale-105 transition duration-300 ease-in-out font-medium rounded-xl text-sm inline-flex items-center justify-center px-4 py-2"
            >
              Live Demo
              <mdicon name="arrow-right" width="20" class="ml-2" />
            </a>
          </div>
        </div>
      </div>
      <div
        class="w-[auto] md:w-[auto] md:item-center bg-[#242738] hidden"
      ></div>
    </div>
  </div>
  <!-- Modal -->
  <ModalImage :image="selectedImage" v-model="showModal" />
</template>
<script setup>
import { ref, onMounted } from "vue";
import ModalImage from "./ModalImage.vue";

const showModal = ref(false);
const selectedImage = ref("");

function openImage(src) {
  showModal.value = true;
  console.log(showModal.value);
  selectedImage.value = new URL(src, import.meta.url).href;
}

const fadeElement = ref(null);

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
