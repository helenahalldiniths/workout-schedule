<template>
  <div class="workout">
    <p id="activity">{{ workout.activity }}</p>
    <p id="duration">Duration: {{ workout.duration }} min</p>
    <p id="week">Week: {{ workout.week }}</p>
  </div>
</template>

<script>
export default {
  name: "WorkoutItem",
  props: {
    workout: Object,
  },
};
</script>

<style scoped>
.workout {
  margin: 10px;
  padding: 10px;
  background-color: lightgray;
}

.workout p {
  margin: 5px;
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
</style>
