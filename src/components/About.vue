<template>
  <section class="about">
    <h2 class="about-title">
      Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
    </h2>
    <p class="about-paragraph">
      Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
      eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam
      voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet
      clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit
      amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
      nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed
      diam voluptua.
    </p>
  </section>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.about {
  display: flex;
  justify-content: space-between;
  flex-direction: column;
  max-width: 1200px;
  margin: 100px auto;
  padding: 0 20px;

  @media (min-width: 768px) {
    flex-direction: row;
  }

  &-title,
  &-paragraph {
    flex: 1;
  }

  &-title {
    font-family: "Open Sans Bold";
    font-size: 28px;
    margin-bottom: 40px;

    @media (min-width: 768px) {
      margin: 0;
      margin-right: 40px;
    }
  }

  &-paragraph {
    font-size: 16px;
    margin-top: 40px;

    @media (min-width: 768px) {
      margin: 0;
      margin-left: 40px;
    }
  }
}
</style>
