<template>
  <div ref="fadeElement" class="opacity-0 invisible">
    <div class="hover:scale-105 transition duration-300 ease-in-out pb-40">
      <div class="gap-4 p-4">
        <div class="bg-thirdly rounded-full shadow-lg shadow-accent p-2">
          <div class="text-white text-xl text-center p-4">
            <p>
              I am excited about new challenges and opportunities. I'm ready to
              contribute, learn, and grow, with the hope of advancing my skills
              and career. Let's get in touch.
            </p>
          </div>
          <div class="gap-2">
            <a
              href="mailto:muh.dhoni@gmail.com"
              target="_blank"
              class="text-white hover:scale-105 transition duration-300 ease-in-out font-medium rounded-lg text-sm inline-flex items-center justify-center p-2"
            >
              <mdicon name="email" width="50" height="50" />
            </a>
            <a
              href="https://www.linkedin.com/in/mdhoni-zahrul-am/"
              target="_blank"
              class="text-white hover:scale-105 transition duration-300 ease-in-out font-medium rounded-xl inline-flex items-center justify-center"
            >
              <mdicon name="linkedin" width="50" height="50" />
            </a>
            <a
              href="https://github.com/doniarifin"
              target="_blank"
              class="text-white hover:scale-105 transition duration-300 ease-in-out font-medium rounded-xl inline-flex items-center justify-center"
            >
              <mdicon name="github" width="50" height="50" />
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
const fadeElement = ref(null);

onMounted(() => {
  if (fadeElement.value) {
    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            fadeElement.value.classList.remove("opacity-0", "invisible");
            fadeElement.value.classList.add("fadeInDown-animation");
            observer.unobserve(fadeElement.value);
          }
        });
      },
      {
        threshold: 0.2,
      }
    );

    observer.observe(fadeElement.value);
  }
});
</script>
