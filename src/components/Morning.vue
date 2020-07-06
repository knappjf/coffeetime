<template>
  <div>{{ message }}</div>
</template>

<script>
const messages = [
  "Rise and shine! It's time for coffee!",
  "Nothing like a cup of joe to start your morning off right",
  "It's going to be a good day, as long as you start off with some coffee",
  "Wakey wakey, time for morning beans!",
];

export default {
  name: "Morning",
  data: () => {
    return {
      name: "Morning",
      message: messages[Math.floor(Math.random() * messages.length)],
    };
  },
};
</script>
