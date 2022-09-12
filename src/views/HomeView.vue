<template>
  <section class="workout-img-section">
    <img
      src="../../public/aerobics.png"
      alt="aerobics"
      id="aerobics-img"
      class="workout-img"
    />
    <img
      src="../../public/yoga.png"
      alt="yoga"
      id="yoga-img"
      class="workout-img"
    />
    <img
      src="../../public/crossfit.png"
      alt="crossfit"
      id="crossfit-img"
      class="workout-img"
    />
  </section>
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

.workout-img-section {
  display: flex;
  justify-content: center;
  gap: 50px;
  flex-direction: row;
  align-items: center;
  margin-top: 10px;
}

.workout-img {
  width: 60px;
}

#yoga-img,
#crossfit-img {
  width: 150px;
}

@media screen and (min-width: 800px) {
  main {
    flex-direction: row;
    margin-left: 10px;
    margin-right: 10px;
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
