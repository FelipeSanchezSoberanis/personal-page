<script setup lang="ts">
import { onMounted, ref, type Ref } from "vue";

const dots: Ref<HTMLSpanElement[] | null> = ref(null);

onMounted(async () => {
  if (dots.value) {
    let waitLonger: boolean = false;
    while (true) {
      for (let i = 0; i < dots.value.length; i++) {
        await delay(250);
        dots.value[i].classList.toggle("high-dot");
      }

      if (waitLonger) await delay(1000);

      waitLonger = !waitLonger;
    }
  }
});

function delay(milliseconds: number): Promise<() => {}> {
  return new Promise((resolve) => {
    setTimeout(resolve, milliseconds);
  });
}
</script>

<template>
  <main>
    <h2>Coming soon <span v-for="_ in 3" ref="dots" class="dot">.</span></h2>
  </main>
</template>

<style scoped lang="scss">
main {
  width: 100vw;
  height: 100vh;
  background-color: black;
}

h2 {
  display: inline-block;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: white;
}

.dot {
  display: inline-block;
  transition: transform 1s ease-out;
}

.high-dot {
  transform: translateY(-10px);
}
</style>
