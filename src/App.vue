<template>
  <div id="app">
    <Nav />
    <Home />
    <Footer />
  </div>
</template>

<script>
import Nav from "@/components/Nav";
import Home from "@/views/Home";
import Footer from "@/components/Footer";

export default {
  components: {
    Nav,
    Home,
    Footer
  }
};
</script>

<style lang="scss">
@font-face {
  font-family: "Open Sans";
  src: url(assets/fonts/Open_Sans/OpenSans-Regular.ttf) format("truetype");
}

@font-face {
  font-family: "Open Sans Bold";
  src: url(assets/fonts/Open_Sans/OpenSans-Bold.ttf) format("truetype");
}

@font-face {
  font-family: "Open Sans Bold Italic";
  src: url(assets/fonts/Open_Sans/OpenSans-BoldItalic.ttf) format("truetype");
}

@import "@/scss/reset.scss";

$white: #fff;
$green: #34c888;
$black: #000;

.button {
  background-color: $white;
  border: 2px solid $green;
  border-radius: 5px;
  color: $green;
  cursor: pointer;
  font-family: "Open Sans Bold";
  font-size: 18px;
  letter-spacing: 0px;
  padding: 10px 30px;
  outline: none;
}
</style>
