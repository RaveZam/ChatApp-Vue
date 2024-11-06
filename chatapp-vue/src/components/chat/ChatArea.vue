<template>
  <div class="w-full pt-16">
    <h1 class="p-4 text-[2vw]">Message Area</h1>
    <div class="p-4 pr-8 mx-4 rounded-2xl text-right">
      <h2 class="mr-4">{{ username }}</h2>
      <div class="bg-blue-400 p-2 rounded-2xl">
        <span class="text-gray-700">
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Vel numquam
          sapiente harum perspiciatis deleniti facilis repellat? Eaque,
          laboriosam quidem architecto nobis ullam dolorum itaque, eveniet
          deleniti qui, sed iure quibusdam.</span
        >
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
const username = ref("Runielle Raven" as string);
</script>
