<template>
  <div>{{ message }}</div>
</template>

<script>
const messages = [
  "It's time for evening beans",
  "Nothing like a post-dinner cup of joe",
  "A dessert coffee sounds pretty good right now",
  "Finish your day off right with some evening beans",
];

export default {
  name: "Evening",
  data: () => {
    return {
      message: messages[Math.floor(Math.random() * messages.length)],
    };
  },
};
</script>
