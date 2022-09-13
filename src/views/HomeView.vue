<template>
  <HeroImage />
  <main>
    <section class="add-workout-section">
      <div class="form-buttons">
        <AppButton
          text="Add Workout"
          @button-clicked="toggleShowForm"
          v-show="!showForm && showButton"
          class="big-btn"
        />
        <AppButton
          text="Hide form"
          color="gray"
          @button-clicked="toggleShowForm"
          v-show="showForm && showButton"
        />
      </div>
      <AddWorkout @add-workout="addWorkout" v-show="showForm" />
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
import HeroImage from "../components/HeroImage.vue";
import AppButton from "../components/AppButton.vue";

export default {
  name: "HomeView",
  components: {
    WorkoutItems,
    AddWorkout,
    HeroImage,
    AppButton,
  },
  data() {
    return {
      workouts: [],
      showForm: false,
      showButton: false,
    };
  },
  methods: {
    onResize() {
      if (window.innerWidth < 821) {
        this.showForm = false;
        this.showButton = true;
      } else {
        this.showForm = true;
        this.showButton = false;
      }
    },
    toggleShowForm() {
      this.showForm = !this.showForm;
    },
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
  mounted() {
    window.addEventListener("resize", this.onResize);
    this.onResize();
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

.form-buttons {
  display: flex;
  justify-content: center;
}

@media screen and (min-width: 821px) {
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
