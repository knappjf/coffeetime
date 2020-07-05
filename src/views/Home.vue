<template>
  <div class="home">
    <Morning v-if="currentTime === timeOfDay.MORNING"></Morning>
    <Afternoon v-else-if="currentTime === timeOfDay.AFTERNOON"></Afternoon>
    <Evening v-else-if="currentTime === timeOfDay.EVENING"></Evening>
    <LateNight v-else-if="currentTime === timeOfDay.LATENIGHT"></LateNight>
    <div v-else>It's always time for some beans</div>
  </div>
</template>

<script>
import Morning from "../components/Morning.vue";
import Afternoon from "../components/Afternoon.vue";
import Evening from "../components/Evening.vue";
import LateNight from "../components/LateNight.vue";
import { DateTime, Interval } from "luxon";

export default {
  name: "Home",
  components: {
    Morning,
    Afternoon,
    Evening,
    LateNight,
  },
  data: function() {
    return {
      currentTime: getTimeOfDay(),
      timeOfDay: timeOfDay,
    };
  },
};

const timeOfDay = {
  MORNING: "Morning",
  AFTERNOON: "Afternoon",
  EVENING: "Evening",
  LATENIGHT: "LateNight",
};

function getTimeOfDay() {
  const dateTime = DateTime.local();

  if (getMorningInterval().contains(dateTime)) {
    return timeOfDay.MORNING;
  } else if (getAfternoonInterval().contains(dateTime)) {
    return timeOfDay.AFTERNOON;
  } else if (getEveningInterval().contains(dateTime)) {
    return timeOfDay.EVENING;
  }
  return timeOfDay.LATENIGHT;
}

function getMorningInterval() {
  const start = DateTime.local().set({
    hour: 4,
    minute: 0,
    second: 0,
    millisecond: 0,
  });

  const end = DateTime.local().set({
    hour: 11,
    minute: 59,
    second: 59,
    millisecond: 999,
  });

  return Interval.fromDateTimes(start, end);
}

function getAfternoonInterval() {
  const start = DateTime.local().set({
    hour: 12,
    minute: 0,
    second: 0,
    millisecond: 0,
  });

  const end = DateTime.local().set({
    hour: 16,
    minute: 59,
    second: 59,
    millisecond: 999,
  });

  return Interval.fromDateTimes(start, end);
}

function getEveningInterval() {
  const start = DateTime.local().set({
    hour: 17,
    minute: 0,
    second: 0,
    millisecond: 0,
  });

  const end = DateTime.local().set({
    hour: 22,
    minute: 59,
    second: 59,
    millisecond: 999,
  });

  return Interval.fromDateTimes(start, end);
}
</script>
