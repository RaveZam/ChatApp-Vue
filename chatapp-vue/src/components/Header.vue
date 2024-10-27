<template>
  <div class="bg-gray-50 h-16 w-screen flex items-center absolute">
    <MessageIcon class="scale-150 ml-4 text-black" />
    <h1 class="p-4">Message App</h1>
  </div>
</template>

<script setup lang="ts">
import MessageIcon from "./MessageIcon.vue";
import { defineComponent } from "vue";

defineComponent({
  name: "Header",
});
</script>
