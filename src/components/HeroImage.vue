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
</template>

<script>
export default {
  name: "HeroImage",
};
</script>

<style scoped>
.workout-img-section {
  display: flex;
  justify-content: center;
  gap: 10px;
  flex-direction: row;
  align-items: center;
  margin-top: 10px;
  padding: 5px;
}

.workout-img {
  width: 35px;
}

#yoga-img,
#crossfit-img {
  width: 95px;
}

@media screen and (min-width: 372px) {
  .workout-img-section {
    gap: 20px;
  }

  .workout-img {
    width: 50px;
  }

  #yoga-img,
  #crossfit-img {
    width: 125px;
  }
}

@media screen and (min-width: 821px) {
  .workout-img-section {
    gap: 50px;
  }

  .workout-img {
    width: 60px;
  }

  #yoga-img,
  #crossfit-img {
    width: 150px;
  }
}
</style>
