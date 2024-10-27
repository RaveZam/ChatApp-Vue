<script setup lang="ts">
defineProps<{ msg: string }>();
</script>

<template>
  <div class="bg-red-500">
    <h1>{{ msg }}</h1>
  </div>
</template>
