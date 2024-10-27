<script setup lang="ts">
import { ref } from "vue";

defineProps<{ msg: string }>();

const count = ref(0);
</script>

<template>
  <div class="bg-red-500">
    <h1>{{ msg }}</h1>
  </div>
</template>
