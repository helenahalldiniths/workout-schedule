<template>
  <div v-for="(workout, index) in workouts" :key="index">
    <WorkoutItem :workout="workout" />
  </div>
</template>

<script>
import WorkoutItem from "./WorkoutItem.vue";
export default {
  name: "WorkoutItems",
  components: {
    WorkoutItem,
  },
  props: {
    workouts: Array,
  },
};
</script>
