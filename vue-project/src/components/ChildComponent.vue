<script setup>
import ParentComponent from './ParentComponent.vue';


const friends = [
    {
        id:'Aman',
        name:'AmanPreet',
        phone:'5566778800',
        email:'Aman@gmail.com',
        isFavorite: true
    },
    {
        id:'Raman',
        name:'RmanPreet',
        phone:'9988776655',
        email:'Rman@gmail.com',
        isFavorite: false
    }
]

const toggleFavoriteStatus = ()=>{
   alert('emiitt')
}

// const toggleFavoriteStatus = (friendId)=>{
//    const identifiedFriend = friends.find(friend => friend.id === friendId);
//    identifiedFriend.isFavorite = !identifiedFriend.isFavorite
// }
</script>

<template>
 
  <Parent-Component v-for="friend in friends" :key="friend.id" :id="friend.id" :name="friend.name" :phone-number="friend.phone" :email-address="friend.email" :is-Favorite = "friend.isFavorite"
   @toggle-favorite="toggleFavoriteStatus" ></Parent-Component>
  
  
</template>
