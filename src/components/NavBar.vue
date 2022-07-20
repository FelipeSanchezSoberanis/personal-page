<script setup lang="ts">
import { RouterLink, useRouter } from "vue-router";
import { ref } from "vue";
import type { Ref } from "vue";

const router = useRouter();

const routes: Ref<Route[]> = ref([
  { path: "/", name: "Home", icon: "fa-solid fa-house" },
  { path: "/about", name: "About", icon: "fa-solid fa-circle-info" },
  { path: "/experience", name: "Experience", icon: "fa-solid fa-briefcase" }
]);

function navTo(path: string): void {
  router.push(path);
}

function isCurrentPath(path: string): boolean {
  let currentPath: string = router.currentRoute.value.path;

  if (path === "/" && currentPath === "/") return true;
  if (path === "/" && currentPath !== "/") return false;

  return currentPath.startsWith(path);
}
</script>

<template>
  <div class="navbar-background">
    <nav class="container">
      <div class="row g-0 justify-content-center align-items-center h-100">
        <div class="logo col pe-3 ps-3">F</div>
        <div
          v-for="route in routes"
          class="navbar-item pb-1 col-3 col-md-auto ps-md-3 pe-md-3 d-flex justify-content-center"
          @click="navTo(route.path)"
          :class="{ 'current-path': isCurrentPath(route.path) }">
          <RouterLink :to="route.path">
            <div class="navbar-text">{{ route.name }}</div>
            <div class="navbar-icon">
              <FontAwesomeIcon
                :icon="route.icon"
                class="navbar-icon"></FontAwesomeIcon>
            </div>
          </RouterLink>
        </div>
      </div>
    </nav>
  </div>
</template>

<style scoped lang="scss">
.navbar-item {
  transition: border $mediumSpeed ease;
  border-bottom: 3px solid transparent;
}

.current-path {
  border-bottom: 3px solid red;
}

.navbar-item:hover {
  cursor: pointer;
}

.navbar-background {
  width: 100%;
  height: $navbarHeight;
  background-color: white;
  position: fixed;
  bottom: 0;
}

.navbar-text {
  display: none;
}

.navbar-icon {
  width: 1.5rem;
  height: 1.5rem;
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
  left: 50%;
  transform: translateX(-50%);
  background-color: white;
}

@include media-breakpoint-up(md) {
  .navbar-background {
    top: 0;
  }

  nav {
    top: 0;
    justify-content: end !important;
    left: 50%;
    transform: translateX(-50%);
  }

  .logo {
    display: block;
  }

  .text-nav-item {
    display: block;
  }

  .navbar-text {
    display: block;
  }

  .navbar-icon {
    display: none;
  }
}
</style>
