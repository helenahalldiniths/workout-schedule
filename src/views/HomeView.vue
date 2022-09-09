<template>
  <main>
    <section class="add-workout-section">
      <AddWorkout @add-workout="addWorkout" />
    </section>
    <section class="show-workouts-section">
      <h1>Workouts:</h1>
      <WorkoutItems
        @complete-workout="completeWorkout"
        @delete-workout="deleteWorkout"
        :workouts="workouts"
      />
    </section>
  </main>
</template>

<script>
import WorkoutItems from "../components/WorkoutItems";
import AddWorkout from "../components/AddWorkout";

export default {
  name: "HomeView",
  components: {
    WorkoutItems,
    AddWorkout,
  },
  data() {
    return {
      workouts: [],
    };
  },
  methods: {
    addWorkout(workout) {
      this.workouts = [...this.workouts, workout];
      console.log("from home", workout);
    },
    completeWorkout(id) {
      this.workouts = this.workouts.map((workout) =>
        workout.id === id
          ? { ...workout, completed: !workout.completed }
          : workout
      );
    },
    deleteWorkout(id) {
      this.workouts = this.workouts.filter((workout) => workout.id !== id);
    },
  },
  created() {
    this.workouts = [
      {
        id: 1,
        activity: "Jog",
        duration: 20,
        week: 1,
        completed: false,
      },
      {
        id: 2,
        activity: "Tennis",
        duration: 50,
        week: 1,
        completed: false,
      },
      {
        id: 3,
        activity: "Power walk",
        duration: 75,
        week: 2,
        completed: false,
      },
    ];
  },
};
</script>

<style scoped>
main {
  display: flex;
  flex-direction: column;
}

section {
  padding: 5px;
}

h1 {
  margin-left: 5px;
}

@media screen and (min-width: 800px) {
  main {
    flex-direction: row;
  }

  .add-workout-section {
    flex-grow: 1;
  }
  .show-workouts-section {
    flex-grow: 3;
    margin-right: 20px;
  }
}
</style>
