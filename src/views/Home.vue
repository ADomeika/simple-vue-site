<template>
  <div class="home">
    <Hero />
    <About />
    <Banner />
    <Services />
  </div>
</template>

<script>
import Hero from "@/components/Hero";
import About from "@/components/About";
import Banner from "@/components/Banner";
import Services from "@/components/Services";

export default {
  components: {
    Hero,
    About,
    Banner,
    Services
  }
};
</script>
