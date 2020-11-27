<template>
  <section class="services">
    <h2 class="services-title">Lorem ipsum dolor sit</h2>
    <div>
      <Carousel
        class="carousel"
        :items="windowWidth < 768 ? 1 : windowWidth < 1025 ? 2 : 3"
        :margin="40"
        :dots="false"
        :nav="false"
      >
        <template slot="prev">
          <i class="fa fa-chevron-left carousel-prev"></i>
        </template>

        <CarouselItem
          title="Lorem ipsum dolor sit amet"
          paragraph="Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum."
          :image="require('../assets/images/service1.jpg')"
        />

        <CarouselItem
          title="Lorem ipsum dolor sit amet"
          paragraph="Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum."
          :image="require('../assets/images/service2.jpg')"
        />

        <CarouselItem
          title="Lorem ipsum dolor sit amet"
          paragraph="Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum."
          :image="require('../assets/images/service3.jpg')"
        />

        <template slot="next">
          <i class="fa fa-chevron-right carousel-next"></i>
        </template>
      </Carousel>
    </div>
  </section>
</template>

<script>
import Carousel from "vue-owl-carousel";
import CarouselItem from "./CarouselItem";

export default {
  data() {
    return {
      windowWidth: window.innerWidth
    };
  },
  components: {
    Carousel,
    CarouselItem
  },
  mounted() {
    this.$nextTick(() => {
      window.addEventListener("resize", this.onResize);
    });
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.onResize);
  },
  methods: {
    onResize() {
      this.windowWidth = window.innerWidth;
    }
  }
};
</script>

<style lang="scss" scoped>
$white: #fff;
$green: #34c888;
$black: #000;

.services {
  max-width: 1200px;
  margin: 100px auto;
  padding: 0 20px;

  &-title {
    font-family: "Open Sans Bold";
    font-size: 40px;
    margin-bottom: 48px;
  }
}

.carousel {
  margin: 0 40px;
  position: relative;

  @media (min-width: 1025px) {
    margin: 0;
  }

  &-prev,
  &-next {
    color: $green;
    cursor: pointer;
    font-size: 40px;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    transition: color 0.3s ease-in-out;

    &:hover {
      color: $black;
    }
  }

  &-prev {
    left: -50px;
  }

  &-next {
    right: -50px;
  }
}
</style>
