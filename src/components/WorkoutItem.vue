<template>
  <div class="workout">
    <div class="workout-info">
      <p id="activity">{{ workout.activity }}</p>
      <p id="duration">Duration: {{ workout.duration }} min</p>
      <p id="week">Week: {{ workout.week }}</p>
    </div>
    <div class="button-div">
      <AppButton text="Completed" color="green" />
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
  padding: 8px;
}

.workout-info p {
  margin: 5px;
}

.button-div {
  margin-right: 10px;
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
  opacity: 0.3;
}
</style>
