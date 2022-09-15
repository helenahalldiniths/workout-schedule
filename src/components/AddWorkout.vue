<template>
  <section class="add-workout-section">
    <h2>Add Workout:</h2>
    <form @submit="onSubmit" class="form">
      <div class="form-control">
        <label>Activity:</label>
        <input
          type="text"
          v-model="newActivity"
          name="newActivity"
          placeholder="Add Activity"
          required
        />
      </div>
      <div class="form-control">
        <label>Duration:</label>
        <input
          type="number"
          v-model="newDuration"
          name="newDuration"
          placeholder="Add Duration (in minutes)"
          required
        />
      </div>
      <div class="form-control">
        <label>Week:</label>
        <input
          type="number"
          v-model="newWeek"
          name="newWeek"
          placeholder="Add the week this workout should happen"
          required
        />
      </div>
      <div class="form-btn">
        <div></div>
        <input type="submit" value="Save Workout" class="big-btn" />
      </div>
    </form>
  </section>
</template>

<script setup>
import { ref } from "vue";
const newActivity = ref("");
const newDuration = ref("");
const newWeek = ref("");
const newId = ref(4);

function onSubmit(event) {
  event.preventDefault();

  if (newDuration.value <= 0) {
    alert("Duration must be more than 0");
    return;
  } else if (newDuration.value < 0) {
    alert("The week must be at least 0");
    return;
  }
  const newWorkout = getNewWorkout();
  emits("add-workout", newWorkout);
  clearForm();
}

function getNewWorkout() {
  return {
    id: newId.value,
    activity: newActivity.value,
    duration: newDuration.value,
    week: newWeek.value,
    completed: false,
  };
}
function clearForm() {
  newId.value = newId.value + 1;
  newActivity.value = "";
  newDuration.value = "";
  newWeek.value = "";
}

const emits = defineEmits(["add-workout"]);
</script>

<style scoped>
.form {
  padding: 0px 20px 0px 10px;
}
.form-control {
  margin-bottom: 20px;
  font-size: 20px;
}

.form-control input {
  width: 95%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 15px;
}

.form-btn {
  display: flex;
  justify-content: space-between;
}
</style>
