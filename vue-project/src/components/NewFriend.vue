<script setup>
import { ref } from 'vue';

const emit = defineEmits(['addFriend'])
const entredName = ref('')
const entredPhone = ref('')
const entredEmail = ref('')

const submitData = () => {
    emit('addFriend',entredName,entredPhone,entredEmail)
}
</script>

<template>
 
 <form action="" @submit.prevent="submitData" >
    <div>
        <label for="">Name:</label>
        <input type="text" name="" id="" v-model="entredName" >
    </div>
    <div>
        <label for="">Phone:</label>
        <input type="text" name="" id=""  v-model="entredPhone">
    </div>
    <div>
        <label for="">Email:</label>
        <input type="text" name="" id="" v-model="entredEmail">
    </div>
    <div>
        <button @click="submitData" >Add Component</button>
    </div>
 </form>
</template>
