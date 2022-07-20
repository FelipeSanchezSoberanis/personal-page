<script setup lang="ts">
import { RouterView } from "vue-router";
import "bootstrap/dist/css/bootstrap.min.css";
import "bootstrap/dist/js/bootstrap.bundle";
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

import NavBar from "./components/NavBar.vue";

gsap.registerPlugin(ScrollTrigger);
</script>

<template>
  <NavBar />
  <RouterView class="container router-view" />
</template>

<style lang="scss">
.router-view {
  margin-bottom: $navbarHeight;
}

@include media-breakpoint-up(md) {
  .router-view {
    margin-bottom: 0;
    margin-top: $navbarHeight;
  }
}
</style>
