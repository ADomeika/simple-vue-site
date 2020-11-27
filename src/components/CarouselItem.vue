<template>
  <div class="carousel-item">
    <img class="carousel-item-image" :src="image" :alt="title + ' image'" />
    <h3 class="carousel-item-title">{{ title }}</h3>
    <p class="carousel-item-paragraph">{{ paragraph }}</p>
  </div>
</template>

<script>
export default {
  props: ["title", "paragraph", "image"]
};
</script>

<style lang="scss" scoped>
.carousel-item {
  &-image {
    width: 100%;
    height: 247px;
    object-fit: cover;
  }

  &-title {
    font-family: "Open Sans Bold";
    font-size: 28px;
    margin: 10px 0;
  }

  &-paragraph {
    font-size: 16px;
  }
}
</style>
