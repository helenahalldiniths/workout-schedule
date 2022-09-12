<template>
  <section>
    <h2>Add Workout:</h2>
    <form @submit="onSubmit" class="form">
      <div class="form-control">
        <label>Activity:</label>
        <input
          type="text"
          v-model="activity"
          name="activity"
          placeholder="Add Activity"
          required
        />
      </div>
      <div class="form-control">
        <label>Duration:</label>
        <input
          type="number"
          v-model="duration"
          name="duration"
          placeholder="Add Duration (in minutes)"
          required
        />
      </div>
      <div class="form-control">
        <label>Week:</label>
        <input
          type="number"
          v-model="week"
          name="week"
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

<script>
export default {
  name: "AddWorkout",
  data() {
    return {
      activity: "",
      duration: "",
      week: "",
      id: 4,
    };
  },
  methods: {
    onSubmit(event) {
      event.preventDefault();

      if (this.duration <= 0) {
        alert("Duration must be more than 0");
        return;
      } else if (this.week < 0) {
        alert("The week must be at least 0");
        return;
      }
      const newWorkout = {
        id: this.id,
        activity: this.activity,
        duration: this.duration,
        week: this.week,
        completed: false,
      };

      this.$emit("add-workout", newWorkout);

      this.id = this.id + 1;
      this.activity = "";
      this.duration = "";
      this.week = "";
    },
  },
};
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
