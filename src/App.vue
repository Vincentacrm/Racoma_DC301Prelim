<script setup>
import { ref } from "vue";
import LearnerProfile from "./components/LearnerProfile.vue";
import CourseList from "./components/CourseList.vue";

const learner = {
  name: "Vincent Racoma",
  program: "BSIT",
  track: "Tech Fields",
  studentId: "18501"
};

const completedLessons = ref(0);

const status = true;

const courses = [
  "HTML",
  "CSS",
  "JavaScript",
  "Vue 3",
  "PHP"
];

function completeLesson() {
  completedLessons.value++;
}

function undoLesson() {
  if (completedLessons.value > 0) {
    completedLessons.value--;
  }
}
</script>

<template>
  <div>
    <h1>Online Course Enrollment System</h1>

    <img
      src="https://scontent.fmnl8-8.fna.fbcdn.net/v/t39.30808-6/627001826_2167269427140195_1318337226009313402_n.jpg?stp=dst-jpg_tt6&cstp=mx206x206&ctp=s206x206&_nc_cat=109&_nc_map=urlgen_bucketless&ccb=1-7&_nc_sid=a5f93a&_nc_eui2=AeFCS7gVVASyLlAC09FKIoI2jVCIuQ-vTSyNUIi5D69NLKU5r4uXESjO2_3sIZcUVHOnfgy9Qv-_w9ZsSqOY0xCI&_nc_ohc=O8m8EMqD-NEQ7kNvwE6f23W&_nc_oc=Adp4Ky84Ft8P3GQhEYeazGY6UuBSRqW7lP6beGtFWvXAaGma5BM8npiVSp_UMiAWXZg&_nc_zt=23&_nc_ht=scontent.fmnl8-8.fna&_nc_gid=0kiZRRZS1PqtDBF4kIbrtw&_nc_ss=7b2a8&oh=00_AQBqkTubJnmdkqXipCM-JTiuw3ZtuKAYh8tOoBeC6yJ0NQ&oe=6A64BD7C"
    />
  </div>
    <LearnerProfile
      :learnerName="learner.name"
      :program="learner.program"
      :track="learner.track"
      :studentId="learner.studentId"
    />

    <h2>
      Course Status:<br>
        {{ status ? "In Progress" : "Completed" }}
    </h2>

    <h2>Completed Lessons: {{ completedLessons }}</h2>
<div>
    <button @click="completeLesson">Complete</button>
    <button @click="undoLesson">Undo</button>
</div>
    <CourseList
      :learnerName="learner.name"
      :courses="courses"
    />

    <h2>
      Classification: <br>
      {{ courses.length >= 5 ? "Advanced Learner" : "Beginner Learner" }}
    </h2>
</template>

