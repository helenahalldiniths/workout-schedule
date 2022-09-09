<template>
  <div class="workout">
    <div :class="[workout.completed ? 'completed' : '', 'workout-info']">
      <p id="activity">{{ workout.activity }}</p>
      <p id="duration">Duration: {{ workout.duration }} min</p>
      <p id="week">Week: {{ workout.week }}</p>
    </div>
    <div class="completeness-div">
      <AppButton
        @button-clicked="$emit('complete-workout', workout.id)"
        text="Completed"
        color="green"
        v-show="!workout.completed"
      />
      <AppButton
        @button-clicked="$emit('delete-workout', workout.id)"
        text="Delete workout"
        color="red"
        v-show="workout.completed"
      />
      <AppButton
        @button-clicked="$emit('complete-workout', workout.id)"
        text="Regret completing"
        color="gray"
        v-show="workout.completed"
      />
    </div>
  </div>
</template>

<script>
import AppButton from "./AppButton.vue";
export default {
  name: "WorkoutItem",
  props: {
    workout: Object,
  },
  components: {
    AppButton,
  },
};
</script>

<style scoped>
.workout {
  display: flex;
  justify-content: space-between;
  background-color: lightgray;
  margin-bottom: 10px;
  align-items: center;
  padding: 10px;
}

.workout-info p {
  margin: 5px;
}

.completeness-div {
  display: flex;
  flex-direction: column;
  margin-right: 10px;
}

.completeness-div p {
  font-style: italic;
  opacity: 0.5;
}

#activity {
  font-size: 20px;
  font-weight: bold;
}

#duration {
  font-size: 15px;
  font-style: italic;
}

#week {
  font-size: 15px;
  font-weight: bold;
}

.completed {
  opacity: 0.5;
}
</style>
