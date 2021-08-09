<template>
  <div id="home">
    <GradientBackground />
    <div class="pattern-wrap">
      <HomePatternTop />
    </div>
    <section id="home-landing">
      <div class="landing-hero">
        <div class="landing-text">
          <Logo />
          <h4>UX Demo built in Vue.js</h4>
        </div>
        <div class="landing-button" @click.prevent="startButton">
          <Button>START</Button>
        </div>
      </div>
    </section>
    <div class="pattern-wrap">
      <HomePatternBottom />
    </div>
  </div>
</template>

<script>
import Logo from "../components/Logo.vue";
import Button from "../components/Button.vue";
import HomePatternBottom from "../components/HomePatternBottom.vue";
import HomePatternTop from "../components/HomePatternTop.vue";
import GradientBackground from "../components/GradientBackground.vue";

export default {
  name: "Home",
  metaInfo: {
    title: "Nova9",
    titleTemplate: null,
  },
  components: {
    Logo,
    Button,
    HomePatternBottom,
    HomePatternTop,
    GradientBackground,
  },
  data() {
    return {
      started: false,
    };
  },
  methods: {
    startButton() {
      this.started = true;
    },
  },
};
</script>

<style lang="scss">
#home-landing {
  display: flex;
  flex-direction: column;
  height: 100vh;
  justify-content: center;
}
.landing-hero {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.landing-text #logo h1 {
  font-size: 4rem;
}
.landing-text #logo h1 span {
  font-size: 3rem;
}
.landing-text h4 {
  font-weight: 300;
  font-size: 1.5rem;
  padding-top: 0.5rem;
}
.landing-button {
  display: flex;
  flex-direction: row;
  justify-content: center;
  margin-top: 4rem;
}
@media screen and (min-width: 600px) {
  .landing-hero {
    flex-direction: row;
    justify-content: space-evenly;
  }
  .landing-button {
    flex-direction: column;
    margin-top: 0;
  }
}
.pattern-wrap {
  position: relative;
  overflow: hidden; // this is broken
}
// .slide-up {
//   transform: translateY(-200px);
// }
// .slide-down {
//   transform: translateY(200px);
// }
</style>
