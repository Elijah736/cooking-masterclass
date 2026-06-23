<template>
  <div class="container">
    <Header :wishlistCount="wishlist.length" />

    <CourseList
      :courses="courses"
      @save-course="saveCourse"
    />
  </div>
</template>

<script setup>
import { ref } from 'vue'
import Header from './components/Header.vue'
import CourseList from './components/CourseList.vue'
import courses from './courses'

const wishlist = ref([])

function saveCourse(id) {
  if (!wishlist.value.includes(id)) {
    wishlist.value.push(id)
  }
}
</script>

<style scoped>
.container {
  margin: auto;
}
</style>