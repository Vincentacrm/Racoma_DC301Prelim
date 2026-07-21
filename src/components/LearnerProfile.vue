<script setup>
defineProps({
  learnerName: String,
  program: String,
  track: String,
  studentId: String
});
</script>

<template>
    <h2>{{ learnerName }}</h2>
    <p>Program: {{ program }}</p>
    <p>Track: {{ track }}</p>
    <p>Student ID: {{ studentId }}</p>
</template>