<script setup>
import { ref } from "vue";
const props = defineProps({
  name: { type: String, require: true },
  phoneNumber: { type: String, require: true },
  emailAddress: { type: String, require: true },
});

let detailsVisible = ref(true);

const friend = ref({
  id: "Aman",
  name: "AmanPreet",
  phoneNumber: "5566778899",
  emailAddress: "Aman@gmail.com",
});

const toggleDetails = () => {
  detailsVisible.value = !detailsVisible.value;
};
</script>

<template>
  <ul>
    <li>
      <h2>{{ name }}</h2>
      <button @click="toggleDetails()">
        {{ detailsVisible ? "Hide" : "Show" }} Details
      </button>
      <ul v-if="detailsVisible">
        <li><strong>Phone:</strong> {{ phoneNumber }}</li>
        <li><strong>Email:</strong> {{ emailAddress }}</li>
      </ul>
    </li>
  </ul>
</template>
