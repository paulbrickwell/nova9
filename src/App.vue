<template>
  <div id="app">
    <div id="app-content">
      <div class="app-constrained">
        <transition name="fade" mode="out-in">
          <router-view />
        </transition>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  metaInfo: {
    titleTemplate: "%s | Nova9",
    meta: [
      { charset: "utf-8" },
      { name: "viewport", content: "width=device-width, initial-scale=1" },
    ],
  },
};
</script>

<style lang="scss">
#app {
  display: flex;
  min-height: 100vh;
  flex-direction: column;
}
#app-content {
  flex: 1;
}
.app-constrained {
  max-width: $page-width;
  margin: 0 auto;
  padding: 0 1rem;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
