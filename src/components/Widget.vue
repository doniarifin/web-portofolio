<template>
  <div v-if="content === 'onlydate'" class="onlydate text-gray-300">
    {{ onlyDate }}
  </div>
  <div v-else-if="content === 'onlytime'" class="onlytime text-gray-300">
    {{ onlyTime }}
  </div>
</template>
<script setup>
import { ref, computed, onMounted, defineProps } from 'vue';

const props = defineProps({
  content: {
    type: String,
    required: true,
    validator: value => ['onlydate', 'onlytime'].includes(value),
  },
});

const date = ref(new Date());
const onlyTime = computed(() => {
  return date.value.toLocaleString('en-Us', { hour: '2-digit', minute: '2-digit', second: '2-digit' });
});

const onlyDate = computed(() => {
  return date.value.toLocaleString('en-US', { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' });
});

onMounted(() => {
  setInterval(() => {
    date.value = new Date();
  }, 1000);
});
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Orbitron');
.onlytime {
  font-family: 'Orbitron';
  font-size: 40px;
}
.onlydate {
  font-family: 'Orbitron';
  font-size: 20px;
}
</style>