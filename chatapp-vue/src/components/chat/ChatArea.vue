<template>
  <div class="w-full pt-16 justify-between flex flex-col">
    <div class="flex justify-between">
      <h1 class="p-4 text-[2vw]">Message Area</h1>
      <input
        class="mr-12 h-12 p-4 border-2 border-gray-800 rounded-md"
        type="text"
        placeholder="input username"
        v-model="username"
      />
    </div>
    <div class="p-4 pr-8 mx-4 rounded-2xl text-right">
      <div class="bg-blue-500 p-4 m-4 rounded-2xl" v-for="message in messages">
        <h2 class="mr-4">{{ message.username }}</h2>
        <span class="text-white">{{ message.message }}</span>
      </div>
    </div>

    <div class="mb-8">
      <form @submit.prevent="submit" class="flex mr-4">
        <input
          class="flex-1 border-2 border-gray-600 rounded-md p-4"
          type="text"
          placeholder="input message"
          v-model="message"
        />
        <button
          type="submit"
          class="bg-blue-500 text-white mx-4 p-4 px-8 rounded-full"
        >
          Send
        </button>
      </form>
    </div>
  </div>
</template>

<script setup lang="ts">
import Pusher from "pusher-js";
import { ref, onMounted } from "vue";

interface ChatMessage {
  username: string;
  message: string;
}

const username = ref("Runielle Raven");
const messages = ref<ChatMessage[]>([]);
const message = ref("");

onMounted(() => {
  Pusher.logToConsole = true;

  const pusher = new Pusher("8f26045999c3fc72d5a0", {
    cluster: "ap1",
  });

  const channel = pusher.subscribe("chat");
  channel.bind("message", (data: ChatMessage) => {
    messages.value.push(data);
  });
});

const submit = async () => {
  await fetch("http://localhost:8000/api/messages", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify({
      username: username.value,
      message: message.value,
    }),
  });
  console.log(messages);
  message.value = "";
};
</script>
