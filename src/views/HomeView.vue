<template>
  <section>
    <AddWorkout @add-workout="addWorkout" />
    <h1>Workouts</h1>
    <WorkoutItems
      @complete-workout="completeWorkout"
      @delete-workout="deleteWorkout"
      :workouts="workouts"
    />
  </section>
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
section {
  padding: 10px;
}
</style>
