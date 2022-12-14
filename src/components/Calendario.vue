<template>
  <div class="flex flex-row border rounded m-5 justify-center">
    <CalendarioDia
      v-for="(e, i) in getWeekDays('es-ES')"
      :diaSemana="e.toUpperCase()"
    />
  </div>
</template>

<script setup>
import { ref } from "vue";
import CalendarioDia from "./CalendarioDia.vue";

function getWeekDays(locale) {
  const today = new Date();
  const first = today.getDate() - today.getDay() + 1;

  const monday = new Date(today.setDate(first));

  let baseDate = monday; // just a Monday
  let weekDays = [];
  for (let i = 0; i < 7; i++) {
    weekDays.push(baseDate.toLocaleDateString(locale, { weekday: "long" }));
    baseDate.setDate(baseDate.getDate() + 1);
  }
  return weekDays;
}
</script>

<style scoped></style>
