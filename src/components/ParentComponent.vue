<script setup>
import { ref } from 'vue';
import ChildComponent from './ChildComponent.vue';

const person = {
  name: 'Fazle Rabbi',
  title: 'Full Stack Developer',
  url: 'https://avatars.githubusercontent.com/u/20722252?v=4'
}

const messageToChild = 'Hello from Parent';
const messageFromChild = ref('');

</script>


<template>
  <div class="p-12 bg-blue-200">
    <p class="mt-4 font-semibold text-2xl">Photo show from child:</p>
    <div class="avatar my-5">
      <div class="w-32 rounded-full shadow-lg border-2">
        <img :src="messageFromChild ? messageFromChild : 'https://brur.ac.bd/wp-content/uploads/2019/03/male.jpg'" />
      </div>
    </div>

    <!-- <h1 class="text-3xl font-semibold text-red-400 my-5">{{ messageFromChild }}</h1> -->
    
    <ChildComponent :person="person" :messageToChild="messageToChild"  v-model:messageFromChild="messageFromChild" />
  </div>
</template>


<style scoped>
/* Add Tailwind CSS classes here if needed */
</style>
