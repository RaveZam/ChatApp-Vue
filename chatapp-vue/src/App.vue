<script setup lang="ts">
import HelloWorld from "./components/HelloWorld.vue";
import Header from "./components/Header.vue";
import MessageIcon from "./components/MessageIcon.vue";
</script>

<template>
  <Header />
  <div class="bg-blue-200">
    <h1>hello</h1>
    <HelloWorld msg="Vite + Vue" />
    <MessageIcon />
  </div>
</template>
