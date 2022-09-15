<template>
  <div v-for="(workout, index) in props.workouts" :key="index">
    <WorkoutItem
      @complete-workout="CompleteWorkout(workout.id)"
      @delete-workout="DeleteWorkout(workout.id)"
      :workout="workout"
    />
  </div>
</template>

<script setup>
import WorkoutItem from "./WorkoutItem.vue";

const props = defineProps({
  workouts: Array,
});

const emits = defineEmits(["complete-workout", "delete-workout"]);

function CompleteWorkout(id) {
  emits("complete-workout", id);
}

function DeleteWorkout(id) {
  emits("delete-workout", id);
}
</script>
