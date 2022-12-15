<script setup>
import ParentComponent from './ParentComponent.vue';


// const friends = [
//     {
//         id:'Aman',
//         name:'AmanPreet',
//         phone:'5566778800',
//         email:'Aman@gmail.com'
//     },
//     {
//         id:'Raman',
//         name:'RmanPreet',
//         phone:'9988776655',
//         email:'Rman@gmail.com'
//     }
// ]

</script>

<template>
 
  <Parent-Component name="Manjinder" phone-number="88997744" email-address="mahi@gmail" is-Favorite = false ></Parent-Component>
  
  <Parent-Component name="AmanDeep" phone-number="74444554" email-address="aman@gmail"  is-Favorite = true></Parent-Component>
</template>
