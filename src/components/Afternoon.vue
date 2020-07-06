<template>
  <div>{{ message }}</div>
</template>

<script>
const messages = [
  "It's time for some afternoon beans",
  "What better way to get through the afternoon crash than a piping hot cup of joe",
  "A cup of coffee ought to get you through the rest of the day",
  "Maybe instead of an afternoon nap you could have some afternoon beans",
];

export default {
  name: "Afternoon Beans",
  data: () => {
    return {
      message: messages[Math.floor(Math.random() * messages.length)],
    };
  },
};
</script>
