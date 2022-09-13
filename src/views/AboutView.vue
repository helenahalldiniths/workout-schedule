<template>
  <main class="about">
    <section class="about-info">
      <h2>How to use:</h2>
      <p>
        This site is used to create a workout plan. You can add workouts to you
        plan and remove them when you have finished them.
      </p>
      <p>
        You add workouts in the form by first entering the activity, e.g. Run.
        Then you write the planed duration(in minutes) of the activity, e.g. 30.
        Lastly you enter which week during you schedule you want to do this
        workout, e.g. 3.
      </p>
    </section>
    <div class="about-img">
      <img
        src="../../public/aerobics.png"
        alt="aerobics"
        id="aerobics-img"
        class="workout-img"
      />
    </div>
  </main>
</template>

<style scoped>
h2 {
  margin: 20px;
  text-align: center;
}

.about-info {
  margin: 0px 30px 0px 30px;
}

.about-img {
  display: flex;
  justify-content: center;
}

img {
  width: 100px;
  height: fit-content;
  padding: 30px;
  margin-right: 60px;
}

@media screen and (min-width: 800px) {
  .about {
    display: flex;
  }

  .about-info p {
    margin: 0px 10px 0px 30px;
  }
}
</style>
