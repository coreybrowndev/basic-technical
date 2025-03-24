<template>
  <div class="card-grid">
    <div v-for="card in cards" :key="card.id" class="card-wrapper" @click="flipCard(card)">
      <div :class="['flip-card-inner', { flipped: card.flipped }]">
        <!-- FRONT -->
        <div class="flip-card-face flip-card-front">
          <Card>
            <template #title>{{ card.front }}</template>
            <p>{{ card.front }}</p>
          </Card>
        </div>

        <!-- BACK -->
        <div class="flip-card-face flip-card-back">
          <Card>
            <template #title>{{ card.back }}</template>
            <p>{{ card.back }}</p>
          </Card>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { reactive } from "vue";

const cards = reactive([
  { id: 1, title: "Card 1", front: "👤 John", back: "📞 555-1234", flipped: false },
  { id: 2, title: "Card 2", front: "👤 Jane", back: "📞 555-5678", flipped: false },
  { id: 3, title: "Card 3", front: "👤 Max", back: "✉️ max@example.com", flipped: false },
  { id: 4, title: "Card 4", front: "👤 Lily", back: "📍 NY", flipped: false },
  { id: 5, title: "Card 5", front: "🛍️ Shoes", back: "$49.99", flipped: false },
  { id: 6, title: "Card 6", front: "🧢 Hat", back: "$19.99", flipped: false },
  { id: 7, title: "Card 7", front: "🧸 Toy", back: "$9.99", flipped: false },
  { id: 8, title: "Card 8", front: "🎧 Headphones", back: "$79.99", flipped: false },
  { id: 9, title: "Card 9", front: "👖 Pants", back: "$79.99", flipped: false },
]);

function flipCard(card) {
  card.flipped = !card.flipped;
}
</script>

<style scoped>
.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 2rem;
  justify-items: center;
  padding: 2rem;
  max-width: 1000px;
  margin: 0 auto;
}

.card-wrapper {
  width: 200px;
  height: 180px;
  perspective: 1000px;
  cursor: pointer;
}

.flip-card-inner {
  width: 100%;
  height: 100%;
  position: relative;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}

.flip-card-inner.flipped {
  transform: rotateY(180deg);
}

.flip-card-face {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.15);
  color: black;
}

.flip-card-front {
  background-color: #fefefe;
}

.flip-card-back {
  background-color: #eef2f7;
  transform: rotateY(180deg);
}

.p-card {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
