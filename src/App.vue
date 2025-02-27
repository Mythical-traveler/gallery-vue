<template>
  <div class="gallery-container">
    <h1 class="title">Gallery</h1>
    <div class="gallery-grid">
      <div v-for="item in galleryItems" :key="item.id" class="gallery-item">
        <div class="gallery-content">
          <img :src="item.image" :alt="item.name" class="gallery-image" />
          <div class="gallery-text">
            <h2>{{ item.name }}</h2>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const galleryItems = ref([
  { id: 1, name: "Delicious Cupcake", image: "/i5.webp" },
  { id: 2, name: "Buffet", image: "/i6.webp" },
  { id: 3, name: "Golden Ratio Pie", image: "/i7.webp" },
  { id: 4, name: "Soma Shake", image: "/i8.webp" }
]);
</script>

<style scoped>
.gallery-container {
  text-align: center;
  padding: 20px;
}
.title {
  font-size: 2rem;
  margin-bottom: 20px;
}
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  justify-items: center;
}
.gallery-item {
  background: #fff;
  border-radius: 10px;
  padding: 15px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
  width: 100%;
  max-width: 400px;
}
.gallery-image {
  width: 100%;
  height: auto;
  object-fit: cover;
  border-radius: 5px;
}
.gallery-text {
  flex: 1;
  text-align: center;
  color: black; 
}
</style>