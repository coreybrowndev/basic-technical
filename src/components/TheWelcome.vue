<script setup>
import { ref } from "vue";

import WelcomeItem from "./WelcomeItem.vue";
import DocumentationIcon from "./icons/IconDocumentation.vue";
import ToolingIcon from "./icons/IconTooling.vue";
import EcosystemIcon from "./icons/IconEcosystem.vue";
import CommunityIcon from "./icons/IconCommunity.vue";
import SupportIcon from "./icons/IconSupport.vue";

const openReadmeInEditor = () => fetch("/__open-in-editor?file=README.md");

const eggsCount = ref(0);
const tortillasCount = ref(0);
const chocolateCount = ref(0);

const incrementEggs = () => eggsCount.value++;
const decrementEggs = () => {
  if (eggsCount.value > 0) {
    eggsCount.value--;
  }
};

const incrementTortillas = () => tortillasCount.value++;
const decrementTortillas = () => {
  if (tortillasCount.value > 0) {
    tortillasCount.value--;
  }
};

const incrementChocolate = () => chocolateCount.value++;
const decrementChocolate = () => {
  if (chocolateCount.value > 0) {
    chocolateCount.value--;
  }
};
</script>

<template>
  <WelcomeItem>
    <template #icon>
      <DocumentationIcon />
    </template>
    <template #heading>List of Items</template>
    Add or remove items from the list below. You can also edit the list item quantity
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <ToolingIcon />
    </template>
    <template #heading>Eggs</template>
    <div style="margin-top: 8px">
      <button @click="decrementEggs">-</button>
      <span style="margin: 0 1rem">{{ eggsCount }}</span>
      <button @click="incrementEggs">+</button>
    </div>
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <EcosystemIcon />
    </template>
    <template #heading>Tortillas</template>
    <div style="margin-top: 8px">
      <button @click="decrementTortillas">-</button>
      <span style="margin: 0 1rem">{{ tortillasCount }}</span>
      <button @click="incrementTortillas">+</button>
    </div>
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <CommunityIcon />
    </template>
    <template #heading>Chocolate</template>
    <div style="margin-top: 8px">
      <button @click="decrementChocolate">-</button>
      <span style="margin: 0 1rem">{{ chocolateCount }}</span>
      <button @click="incrementChocolate">+</button>
    </div>
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <SupportIcon />
    </template>
    <template #heading>Ordering some Items</template>
    <div style="margin-top: 8px">
      <p>Total Eggs: {{ eggsCount }}</p>
      <p>Total Tortillas: {{ tortillasCount }}</p>
      <p>Total Chocolate: {{ chocolateCount }}</p>
    </div>
  </WelcomeItem>
</template>
