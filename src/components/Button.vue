<template>
  <div>
    <router-link v-if="to" class="button" :to="to"><slot></slot></router-link>
    <div v-if="!to" class="button"><slot></slot></div>
  </div>
</template>

<script>
import "vanilla-tilt";
import VanillaTilt from "vanilla-tilt";
export default {
  props: {
    to: {
      type: String,
      default: null,
    },
  },
  mounted() {
    VanillaTilt.init(document.querySelector(".button"), {
      max: 10,
      speed: 100,
      reverse: true,
      easing: "cubic-bezier(.03,.98,.52,.99)"
    });
  },
};
</script>

<style lang="scss">
.button {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: $splash-color;
  color: $secondary-color;
  text-decoration: none;
  border-radius: 0.5rem;
  padding: 0 1rem;
  min-width: 8rem;
  height: 3rem;
  cursor: pointer;
  transition: all 0.1s linear;
  &:hover {
    // box-shadow: 0.5rem 0.5rem 0 rgba(0, 0, 0, 0.1);
    background-color: $splash-hover;
  }
}
</style>
