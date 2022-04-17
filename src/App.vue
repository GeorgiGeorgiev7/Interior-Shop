<template>
  <div class="app">
    <div class="background" />
    <the-heading />
    <the-room />
    <the-footer />
  </div>
</template>

<script>
import TheHeading from "./components/TheHeading.vue";
import TheFooter from "./components/TheFooter.vue";
import TheRoom from "./components/TheRoom.vue";

export default {
  components: { TheHeading, TheFooter, TheRoom },
};
</script>

<style>
body {
  margin: 0;
  padding: 0;
  background-color: black;
  cursor: default;
}

.background {
  position: absolute;
  top: 0;
  left: 0;
  min-width: 100%;
  min-height: 100%;
  max-width: 100%;
  max-height: 100%;
  background-image: url("./assets/background_image.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  opacity: 0.15;
  overflow: hidden;
}
</style>