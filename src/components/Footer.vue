<template>
  <footer class="footer">
    <div class="footer-inner">
      <div class="rules">
        <p class="rules-terms">Terms &amp; Conditions</p>
        <p class="rules-policy">Privacy Policy</p>
      </div>
      <div class="social">
        <i class="fab fa-facebook" />
        <i class="fab fa-twitter" />
        <i class="fab fa-linkedin" />
      </div>
    </div>
  </footer>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
$white: #fff;
$green: #34c888;
$black: #000;

.footer {
  background-color: $black;
  color: $white;
  padding: 50px 20px;

  &-inner {
    align-items: center;
    display: flex;
    justify-content: space-between;
    max-width: 1200px;
    margin: 0 auto;
    flex-direction: column;

    @media (min-width: 768px) {
      flex-direction: row;
    }
  }
}

.rules {
  display: flex;
  font-size: 18px;

  &-terms {
    margin-right: 16px;
  }

  &-policy {
    margin-left: 16px;
    position: relative;

    &:before {
      content: "";
      position: absolute;
      top: 0;
      left: -16px;
      height: 18px;
      border-left: 1px solid $white;
    }
  }
}

.social {
  margin-top: 40px;

  @media (min-width: 768px) {
    margin-top: 0;
  }
}

.fab {
  color: $green;
  font-size: 18px;

  &:not(:first-child) {
    margin-left: 40px;
  }
}
</style>
