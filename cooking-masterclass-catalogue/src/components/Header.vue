<template>
    <header class="header">
      <h1>Cooking Masterclass</h1>
      <div class="wishlist"><br>
        <p>❤️ Wishlist: {{ wishlistCount }}</p>
        </div>
    </header>
</template>
  
  <script setup>
  defineProps({
    wishlistCount: Number
  })
  </script>
  
  <style scoped>
  .header{
    width: 1000px;
    padding: 20px;
    margin-left: 50px;
  }

  h1{
    text-align: center;
  }
  </style>