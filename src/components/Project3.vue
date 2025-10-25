<template>
  <div ref="fadeElement" class="opacity-0 invisible">
    <div
      class="justify-center mx-[auto] hover:scale-105 transition duration-300 ease-in-out pb-10"
    >
      <div class="lg:flex grid mx-auto gap-4 p-6 lg:p-2">
        <div class="w-[auto] md:w-[auto] md:item-center rounded">
          <div class="grid text-gray-300 text-justify mt-10">
            <h1 class="text-white text-xl font-bold">HRIS RS-JIH</h1>
          </div>
          <div class="grid text-gray-300 text-justify mt-6">
            <p>
              A modern and responsive hospital management website for RS JIH
              (Rumah Sakit JIH), designed to provide staff with a seamless
              digital experience. The frontend is built using Nuxt.js, featuring
              an intuitive user interface, dynamic content display, and
              optimized performance for both desktop and mobile users.
            </p>
          </div>
          <div class="text-gray-300 text-xl text-justify mt-6">
            <p class="text-secondary font-bold">.NET, Nuxt.Js, SQL Server.</p>
          </div>
          <div class="mb-10 mt-10">
            <a
              href="https://hris.rs-jih.co.id/"
              target="_blank"
              class="text-white bg-secondary hover:scale-105 transition duration-300 ease-in-out font-medium rounded-xl text-sm inline-flex items-center justify-center px-4 py-2"
            >
              Website
              <mdicon name="arrow-right" width="20" class="ml-2" />
            </a>
          </div>
        </div>
        <div class="w-[auto] md:w-[auto] md:item-center opacity-100">
          <div class="rounded">
            <div
              class="p-3 cursor-pointer"
              @click="openImage('/images/project3.png')"
            >
              <img
                src="/images/project3.png"
                alt=""
                class="rounded shadow-[0px_0px_13px_0px_rgb(209_213_219)]"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <ModalImage :image="selectedImage" v-model="showModal" />
</template>
<script setup>
import { ref, onMounted } from "vue";
import ModalImage from "./ModalImage.vue";

const showModal = ref(false);
const selectedImage = ref("");

function openImage(src) {
  showModal.value = true;
  selectedImage.value = new URL(src, import.meta.url).href;
}

const fadeElement = ref(null);

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          fadeElement.value.classList.remove("opacity-0", "invisible");
          fadeElement.value.classList.add("fadeInLeft-animation");
          observer.unobserve(fadeElement.value);
        }
      });
    },
    {
      threshold: 0.2,
    }
  );
  if (fadeElement.value) {
    observer.observe(fadeElement.value);
  }
});
</script>
