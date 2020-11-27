<template>
  <header class="header">
    <nav class="navbar">
      <button class="navbar-toggle" @click="toggleMenu">
        <span class="navbar-toggle-icon"></span>
      </button>

      <div class="navbar-links" v-show="menuOpen">
        <ul class="navbar-nav">
          <li class="nav-item">
            <a class="nav-link" href="#aboutus">About us</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#team">Team</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#services">Services</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#contactus">Contact us</a>
          </li>
        </ul>

        <button class="button">Login</button>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  data() {
    return {
      menuOpen: false,
      windowWidth: window.innerWidth
    };
  },
  watch: {
    windowWidth(newWidth) {
      if (newWidth > 767) {
        this.menuOpen = true;
      }
    }
  },
  mounted() {
    this.$nextTick(() => {
      window.addEventListener("resize", this.onResize);
      if (this.windowWidth > 767) {
        this.menuOpen = true;
      }
    });
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.onResize);
  },
  methods: {
    toggleMenu() {
      this.menuOpen = !this.menuOpen;
    },
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
$dark-grey: #231f20;

.header {
  background-color: $white;
  left: 0;
  position: fixed;
  right: 0;
  top: 0;
  z-index: 9;
}

.navbar {
  display: flex;
  justify-content: flex-end;
  max-width: 1200px;
  margin: 0 auto;
  padding: 18px;

  &-toggle {
    background-color: transparent;
    border: 0;
    outline: none;

    @media (min-width: 768px) {
      display: none;
    }
  }

  &-toggle-icon {
    border: 0;
    position: relative;
    margin-top: 8px;
    margin-bottom: 8px;
    user-select: none;
  }

  &-toggle-icon,
  &-toggle-icon:before,
  &-toggle-icon:after {
    display: block;
    width: 32px;
    height: 3px;
    background-color: $black;
    outline: 1px solid transparent;
  }

  &-toggle-icon:before,
  &-toggle-icon:after {
    content: "";
    left: 0;
    position: absolute;
  }

  &-toggle-icon:before {
    top: -8px;
  }

  &-toggle-icon:after {
    top: 8px;
  }

  &-links {
    @media (max-width: 767px) {
      top: 50px;
      position: absolute;
      background-color: white;
      left: 0;
      padding: 20px;
      width: 100%;
    }

    @media (min-width: 768px) {
      display: flex;
      justify-content: flex-end;
    }
  }

  &-nav {
    @media (min-width: 768px) {
      display: flex;
      justify-content: flex-end;
    }
  }
}

.nav {
  &-item {
    padding: 16px 0;
    position: relative;

    @media (min-width: 768px) {
      padding: 16px;
    }

    &:not(:first-child) {
      &:before {
        border-top: 1px solid $black;
        content: "";
        position: absolute;
        left: 0;
        top: 0;
        width: 100%;

        @media (min-width: 768px) {
          border-top: 0;
          border-left: 1px solid $black;
          height: 18px;
          left: 0;
          top: 50%;
          transform: translateY(-50%);
        }
      }
    }
  }

  &-link {
    color: $dark-grey;
    text-decoration: none;
    font-size: 18px;
    transition: color 0.3s ease-in-out;

    &:hover {
      color: $green;
    }
  }
}
</style>
