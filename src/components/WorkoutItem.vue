<template>
  <div class="workout">
    <div :class="[props.workout.completed ? 'completed' : '', 'workout-info']">
      <p id="activity">{{ props.workout.activity }}</p>
      <p id="duration">Duration: {{ props.workout.duration }} min</p>
      <p id="week">Week: {{ props.workout.week }}</p>
    </div>
    <div class="completeness-div">
      <AppButton
        @button-clicked="CompleteWorkout(props.workout.id)"
        text="Completed"
        v-show="!props.workout.completed"
      />
      <AppButton
        @button-clicked="CompleteWorkout(props.workout.id)"
        text="Regret"
        color="gray"
        v-show="props.workout.completed"
      />
      <AppButton
        @button-clicked="DeleteWorkout(props.workout.id)"
        text="Delete"
        color="red"
        v-show="props.workout.completed"
      />
    </div>
  </div>
</template>

<script setup>
import AppButton from "./AppButton.vue";
const props = defineProps({ workout: Object });

const emits = defineEmits(["complete-workout", "delete-workout"]);

function CompleteWorkout(id) {
  emits("complete-workout", id);
}
function DeleteWorkout(id) {
  emits("delete-workout", id);
}
</script>

<style scoped>
.workout {
  display: flex;
  justify-content: space-between;
  background-color: rgb(232, 232, 232);
  border-radius: 10px;
  margin-bottom: 10px;
  align-items: center;
  padding: 10px;
  min-height: 100px;
  margin-left: 20px;
  margin-right: 20px;
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
