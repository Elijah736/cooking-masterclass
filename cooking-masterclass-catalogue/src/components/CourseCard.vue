<template>
    <div class="container-cards">
        <div class="card">
          <h2>{{ course.title }}</h2>
  
          <p><strong>Chef:</strong> {{ course.chef }}</p>
          <p><strong>Level:</strong> {{ course.level }}</p>
          <p><strong>Price:</strong> R{{ course.price }}</p>
  
          <p
            :class="course.available ? 'available' : 'sold-out'"
          >
            {{ course.available ? "Available" : "Sold Out" }}
          </p>
  
          <button
            @click="saveCourse"
            :disabled="!course.available"
          >
            Save Course
          </button>
        </div>
    </div>
  </template>
  
  <script setup>
    const props = defineProps({
        course: Object
    })
  const emit = defineEmits(["save-course"])

  function saveCourse() {
    emit('save-course', props.course.id)
  }
  </script>
  
  <style scoped>
  
  .container-cards{
    display: flex;
    justify-content: center;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 20px
  }
  
  .card {
    width: 400px;
    background: white;
    border-radius: 10px;
    padding: 20px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s ease;
  }
  
  .card:hover {
    transform: translateY(-5px);
  }
  
  .card h2 {
    color: #006341;
    margin-bottom: 10px;
  }
  
  .card p {
    margin: 8px 0;
  }
  
  .available {
    color: green;
    font-weight: bold;
  }
  
  .sold-out {
    color: red;
    font-weight: bold;
  }
  
  button {
    margin-top: 12px;
    padding: 10px 15px;
    border: none;
    border-radius: 5px;
    background-color: #006341;
    color: white;
    cursor: pointer;
    width: 100%;
  }
  
  button:hover {
    opacity: 0.9;
  }
  
  button:disabled {
    background-color: #999;
    cursor: not-allowed;
  }
  </style>