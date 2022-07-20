<script setup lang="ts">
import { RouterLink } from "vue-router";
import { ref } from "vue";
import type { Ref } from "vue";

const routes: Ref<Route[]> = ref([
  { path: "/", name: "Home" },
  { path: "/about", name: "About" },
  { path: "/experience", name: "Experience" }
]);
</script>

<template>
  <nav class="row g-0 justify-content-center align-items-center">
    <div class="logo col pe-3 ps-3">F</div>
    <div
      v-for="route in routes"
      class="text-nav-item col-2 col-md-auto ps-md-3 pe-md-3 text-center">
      <RouterLink :to="route.path">{{ route.name }}</RouterLink>
    </div>
  </nav>
</template>

<style scoped lang="scss">
.text-nav-item {
  display: none;
}

.logo {
  display: none;
}

a {
  color: inherit;
  text-decoration: inherit;
}

nav {
  position: fixed;
  width: 100%;
  height: $navbarHeight;
  bottom: 0;
  background-color: white;
}

@include media-breakpoint-up(md) {
  nav {
    top: 0;
    justify-content: end !important;
  }

  .logo {
    display: block;
  }

  .text-nav-item {
    display: block;
  }
}
</style>
