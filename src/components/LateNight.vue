<template>
  <div>{{ message }}</div>
</template>

<script>
const messages = [
  "It's time for late night beans",
  "Boy you're up late, better put on another pot of coffee",
  "Boss got you working late? Some late night beans should make it better",
  "You've made it this far, might as well have another cup of joe to get through the night",
];

export default {
  name: "LateNight",
  data: () => {
    return {
      name: "LateNight",
      message: messages[Math.floor(Math.random() * messages.length)],
    };
  },
};
</script>
