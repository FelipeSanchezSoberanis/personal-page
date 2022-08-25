<script setup lang="ts">
import { ref } from "vue";
import { RouterLink } from "vue-router";
import type { Ref } from "vue";

interface Route {
  name: string;
  path: string;
}

const routes: Route[] = [{ name: "Home", path: "/" }];
const closeNavBarBtn: Ref<HTMLButtonElement | null> = ref(null);
</script>

<template>
  <nav class="navbar navbar-expand-md bg-light fixed-top">
    <div class="container">
      <a class="navbar-brand" href="#">Offcanvas navbar</a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="offcanvas"
        data-bs-target="#offcanvasNavbar"
        aria-controls="offcanvasNavbar">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div
        class="offcanvas offcanvas-end"
        tabindex="-1"
        id="offcanvasNavbar"
        aria-labelledby="offcanvasNavbarLabel">
        <div class="offcanvas-header">
          <button
            ref="closeNavBarBtn"
            type="button"
            class="btn-close"
            data-bs-dismiss="offcanvas"
            aria-label="Close"></button>
        </div>
        <div class="offcanvas-body">
          <ul class="navbar-nav justify-content-end flex-grow-1 pe-3">
            <li v-for="route in routes" class="nav-item">
              <router-link :to="{ path: route.path }" class="nav-link">{{
                route.name
              }}</router-link>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </nav>
</template>

<style scoped lang="scss"></style>
