<script setup>
import { ref } from "vue";

const props = defineProps({
  name: { type: String, required: true },
  phoneNumber: { type: String, required: true },
  emailAddress: { type: String, required: true },
  isFavorite: { type: String, required: false, default: '0', validator : function(value) {return value === '0' || value ==='1'} },
});

const detailsVisible = ref(true);

// const friend = ref({
//   id: "Aman",
//   name: "AmanPreet",
//   phoneNumber: "5566778899",
//   emailAddress: "Aman@gmail.com",
// });

const friendisFavorite = ref('isFavorite')

const toggleDetails = () => {
  detailsVisible.value = !detailsVisible.value;
};

const toggleFavorite = () => {
  if(friendisFavorite.value === '1'){
    friendisFavorite.value = '0'
  }else {
    friendisFavorite.value = '1'
  }
}
</script>

<template>
  <ul>
    <li>
      <h2>{{ name }} {{friendisFavorite === '1' ? '(Favorite)' : ''}} </h2>
      <button @click="toggleFavorite" >Toggle Favorite</button>
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
