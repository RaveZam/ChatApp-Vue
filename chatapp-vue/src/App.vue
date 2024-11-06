<template>
  <div>
    <Header />
    <div class="flex">
      <Sidebar />
      <ChatArea />
    </div>
  </div>
</template>

<script setup lang="ts">
import Header from "./components/Header.vue";
import Sidebar from "./components/Sidebar.vue";
import ChatArea from "./components/chat/ChatArea.vue";
</script>
