<template>
  <section class="hero">
    <img
      alt="Hero banner"
      class="hero-banner"
      src="../assets/images/hero-banner.jpg"
    />
    <div class="hero-inner">
      <h1 class="hero-logo">Logo</h1>
      <button class="button" @click="openModal">
        Play video<i class="fas fa-play play-icon"></i>
      </button>
    </div>
    <div v-if="modalOpen" class="modal-overlay">
      <div class="modal-inner" @click.self="closeModal">
        <div class="modal">
          <video
            src="https://player.vimeo.com/external/250591675.hd.mp4?s=683b6a97dac3cb88559fa678af378da3929369fa&amp;profile_id=175"
            autoplay=""
            loop=""
            :muted="false"
            controls=""
            poster="https://i.vimeocdn.com/video/857036244_640.jpg"
            controlslist="nodownload"
            class="video"
          ></video>
        </div>
        <i class="fas fa-times close-icon" @click="closeModal"></i>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      modalOpen: false
    };
  },
  methods: {
    openModal() {
      this.modalOpen = true;
    },
    closeModal() {
      this.modalOpen = false;
    }
  }
};
</script>

<style lang="scss" scoped>
$white: #fff;
$green: #34c888;
$black: #000;

.hero {
  height: 100vh;
  position: relative;
  width: 100%;

  &-banner {
    display: block;
    height: 100%;
    object-fit: cover;
    width: 100%;
  }

  &-inner {
    left: 50%;
    position: absolute;
    text-align: center;
    top: 50%;
    transform: translateX(-50%) translateY(-50%);
  }

  &-logo {
    color: $white;
    font-family: "Open Sans Bold";
    font-size: 60px;
    margin-bottom: 60px;

    @media (min-width: 768px) {
      font-size: 160px;
      margin-bottom: 100px;
    }
  }
}

.play-icon {
  color: $green;
  font-size: 18px;
  margin-left: 10px;
}

.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba($black, 0.6);
  z-index: 10;
}

.modal-inner {
  position: relative;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal {
  width: 90%;
}

.video {
  display: block;
  height: 100%;
  width: 100%;
}

.close-icon {
  color: $white;
  cursor: pointer;
  font-size: 30px;
  position: absolute;
  right: 40px;
  top: 40px;
}
</style>
