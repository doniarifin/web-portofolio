<template>
  <slot name="onlytime" :item="onlyTime">
    <div class="onlytime text-[#fcffe7]">
      {{ onlyTime }}
    </div>
  </slot>
  <slot name="onlydate" :item="onlyDate">
    <div class="onlydate text-[#fcffe7]">
      {{ onlyDate }}
    </div>
  </slot>
</template>
<script setup>
import { ref, computed, onMounted } from 'vue';

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