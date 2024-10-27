<template>
  <div class="w-1/6 h-screen pt-20">
    <div class="flex p-4 hover:bg-gray-300 duration-300 cursor-pointer">
      <ProfileIcon class="scale-150 mt-1 mr-2" />
      <h1>Runielle Raven</h1>
    </div>
  </div>
</template>

<script setup lang="ts">
import { defineComponent } from "vue";
import ProfileIcon from "./ProfileIcon.vue";

defineComponent({
  name: "sidebar",
});
</script>
