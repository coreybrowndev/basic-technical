<script setup>
import { ref } from "vue";

import WelcomeItem from "./WelcomeItem.vue";
import DocumentationIcon from "./icons/IconDocumentation.vue";
import SupportIcon from "./icons/IconSupport.vue";

const cars = ref([
  { id: 1, name: "Lamborghini Aventador", image: "https://images.pexels.com/photos/2127733/pexels-photo-2127733.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2" },
  {
    id: 2,
    name: "Ferrari F8 Tributo",
    image: "https://images.pexels.com/photos/29834967/pexels-photo-29834967/free-photo-of-luxury-car-in-dubai-marina-skyline.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
  },
  {
    id: 3,
    name: "Porsche 911 Turbo",
    image: "https://images.pexels.com/photos/30313799/pexels-photo-30313799/free-photo-of-classic-porsche-racing-through-ankara-forest.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
  },
  {
    id: 4,
    name: "McLaren 720S",
    image: "https://images.pexels.com/photos/27985144/pexels-photo-27985144/free-photo-of-mclaren-650s-widebody-liberty-walk.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2",
  },
]);
</script>

<template>
  <WelcomeItem>
    <template #icon>
      <DocumentationIcon />
    </template>
    <template #heading>Supercar Gallery</template>
    Explore the latest and most exotic supercars. Click the heart icon to like your favorite!
  </WelcomeItem>

  <div style="display: flex; gap: 3rem; flex-wrap: wrap; justify-content: center; margin-top: 20px">
    <div v-for="car in cars" :key="car.id" style="border: 1px solid #ccc; padding: 1rem; border-radius: 8px; text-align: center; width: 200px">
      <img :src="car.image" :alt="car.name" style="width: 100%; border-radius: 8px; height: 100%; object-fit: cover" />
      <h3>{{ car.name }}</h3>
    </div>
  </div>
</template>
