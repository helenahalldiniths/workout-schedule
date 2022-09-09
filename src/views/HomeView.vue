<template>
  <section>
    <h1>This is an home page</h1>
    <WorkoutItems :workouts="workouts" />
  </section>
</template>

<script>
import WorkoutItems from "../components/WorkoutItems";

export default {
  name: "HomeView",
  components: {
    WorkoutItems,
  },
  data() {
    return {
      workouts: [],
    };
  },
  created() {
    this.workouts = [
      {
        id: 1,
        activity: "Jog",
        duration: 20,
        week: 1,
        completed: true,
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
