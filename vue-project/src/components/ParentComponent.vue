<script setup>
import { ref } from "vue";


const props = defineProps({
  id: {type:String, required: true},
  name: { type: String, required: true },
  phoneNumber: { type: String, required: true },
  emailAddress: { type: String, required: true },
  isFavorite: { type: Boolean, required: false, default: false,  },
});

const emit = defineEmits(['toggleFavorite'])


const detailsVisible = ref(true);

const toggleDetails = () => {
  detailsVisible.value = !detailsVisible.value;
};

const toggleFavorite = () => {
 emit('toggleFavorite')
}
</script>

<template>

  <ul>
    <li>
      <h2>{{ name }} {{isFavorite === '1' ? '(Favorite)' : ''}} </h2>
      
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
