<template>
    <div class="course-grid">
      <CourseCard
        v-for="course in courses"
        :key="course.id"
        :course="course"
        @save-course="saveCourse"
      />
    </div>
  </template>
  
  <script setup>
  import CourseCard from "./CourseCard.vue"
  
  defineProps({
    courses: Array
  })
  
  const emit = defineEmits(["save-course"])
  
  const saveCourse = (id) => {
    emit("save-course", id)
  }
  </script>
  