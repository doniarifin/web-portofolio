<template>
  <div
    v-if="modelValue"
    class="fixed inset-0 z-[9999] bg-black bg-opacity-80 flex items-center justify-center z-50"
    @click.self="close"
  >
    <div class="relative max-w-4xl w-full">
      <div
        class="absolute top-0 right-0 text-red-500 font-bold text-xl cursor-pointer"
        @click="close"
      >
        <mdicon name="close" width="40" height="40" class="animate-fadeIn" />
      </div>
      <div>
        <img
          :src="image"
          alt="Fullscreen"
          class="max-h-[90vh] w-full object-contain rounded shadow-lg animate-fadeIn"
        />
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  image: { type: String, default: "" },
  modelValue: { type: Boolean, default: false },
});

const emit = defineEmits(["update:modelValue"]);

const close = () => {
  emit("update:modelValue", false);
};
</script>

<style scoped>
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: scale(0.95);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}
.animate-fadeIn {
  animation: fadeIn 0.3s ease-out;
}
</style>
