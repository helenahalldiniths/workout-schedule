<template>
  <div v-for="(workout, index) in workouts" :key="index">
    <WorkoutItem
      @complete-workout="$emit('complete-workout', workout.id)"
      @delete-workout="$emit('delete-workout', workout.id)"
      :workout="workout"
    />
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
  emits: ["complete-workout", "delete-workout"],
};
</script>
