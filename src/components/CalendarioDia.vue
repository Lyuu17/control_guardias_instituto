<template>
  <div class="flex flex-col pr-5">
    <p>{{ diaSemana }}</p>
  </div>
</template>

<script setup>
const props = defineProps({
  diaSemana: {
    type: String,
    required: true,
  },
});
</script>
