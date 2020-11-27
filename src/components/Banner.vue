<template>
  <section class="banner">
    <div class="banner-inner">
      <h2 class="banner-text">
        Lorem ipsum dolor sit amet, consetetur
      </h2>
      <button class="button">Button</button>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
$green: #34c888;
$white: #fff;

.banner {
  background: url(../assets/images/banner.jpg);
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  border-top: 10px solid $green;
  border-bottom: 10px solid $green;
  padding: 114px 20px;

  &-inner {
    max-width: 1200px;
    margin: 0 auto;
  }

  &-text {
    color: $white;
    font-family: "Open Sans Bold Italic";
    font-size: 80px;
    max-width: 950px;
    line-height: 90px;
    margin-bottom: 30px;
  }
}

.button {
  background-color: $green;
  color: $white;
}
</style>
