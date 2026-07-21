<script setup>
defineProps({
  learnerName: String,
  courses: Array
});
</script>

<template>
    <h2>Courses</h2>

    <ul>
      <li v-for="course in courses" :key="course">
        {{ course }}
      </li>
    </ul>
</template>