<script setup lang="ts">
import Firma from "@/components/Firma.vue";
</script>

<template>
  <main>
    <div class="landing-block">
      <Firma class="firma" />
    </div>
  </main>
</template>

<style scoped lang="scss">
.landing-block {
  width: 100%;
  height: 100vh;
  background-image: url("@/assets/software-development-wallpaper.jpg");
  position: relative;
}

.firma {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  width: 75%;
}
</style>
