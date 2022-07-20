<script setup lang="ts">
import { gsap } from "gsap";
import { onMounted } from "vue";

onMounted(() => {
  gsap.from("#landing-text-one", {
    scrollTrigger: ".landing-content",
    opacity: 0,
    x: -100
  });

  gsap.from("#landing-text-two", {
    scrollTrigger: ".landing-content",
    opacity: 0,
    x: -100,
    delay: 0.25
  });

  gsap.from("#testing", {
    scrollTrigger: "#testing",
    opacity: 0,
    x: -100,
    delay: 0.25
  });
});
</script>

<template>
  <main>
    <img src="software-development-wallpaper.jpg" alt="background" />

    <div class="landing-content">
      <h1 id="landing-text-one" class="landing-text">Title</h1>
      <h2 id="landing-text-two" class="landing-text">Subtitle</h2>
    </div>

    <section id="testing">
      Lorem ipsum dolor, sit amet consectetur adipisicing elit. Provident
      explicabo fugit tempore voluptatem reprehenderit expedita ea, tempora
      dolorem enim voluptates eaque nisi labore reiciendis iusto et repudiandae
      quod minima distinctio! Lorem ipsum dolor, sit amet consectetur
      adipisicing elit. Provident explicabo fugit tempore voluptatem
      reprehenderit expedita ea, tempora dolorem enim voluptates eaque nisi
      labore reiciendis iusto et repudiandae quod minima distinctio! Lorem ipsum
      dolor, sit amet consectetur adipisicing elit. Provident explicabo fugit
      tempore voluptatem reprehenderit expedita ea, tempora dolorem enim
      voluptates eaque nisi labore reiciendis iusto et repudiandae quod minima
      distinctio! Lorem ipsum dolor, sit amet consectetur adipisicing elit.
      Provident explicabo fugit tempore voluptatem reprehenderit expedita ea,
      tempora dolorem enim voluptates eaque nisi labore reiciendis iusto et
      repudiandae quod minima distinctio! Lorem ipsum dolor, sit amet
      consectetur adipisicing elit. Provident explicabo fugit tempore voluptatem
      reprehenderit expedita ea, tempora dolorem enim voluptates eaque nisi
      labore reiciendis iusto et repudiandae quod minima distinctio! Lorem ipsum
      dolor, sit amet consectetur adipisicing elit. Provident explicabo fugit
      tempore voluptatem reprehenderit expedita ea, tempora dolorem enim
      voluptates eaque nisi labore reiciendis iusto et repudiandae quod minima
      distinctio! Lorem ipsum dolor, sit amet consectetur adipisicing elit.
      Provident explicabo fugit tempore voluptatem reprehenderit expedita ea,
      tempora dolorem enim voluptates eaque nisi labore reiciendis iusto et
      repudiandae quod minima distinctio! Lorem ipsum dolor, sit amet
      consectetur adipisicing elit. Provident explicabo fugit tempore voluptatem
      reprehenderit expedita ea, tempora dolorem enim voluptates eaque nisi
      labore reiciendis iusto et repudiandae quod minima distinctio! Lorem ipsum
      dolor, sit amet consectetur adipisicing elit. Provident explicabo fugit
      tempore voluptatem reprehenderit expedita ea, tempora dolorem enim
      voluptates eaque nisi labore reiciendis iusto et repudiandae quod minima
      distinctio! Lorem ipsum dolor, sit amet consectetur adipisicing elit.
      Provident explicabo fugit tempore voluptatem reprehenderit expedita ea,
      tempora dolorem enim voluptates eaque nisi labore reiciendis iusto et
      repudiandae quod minima distinctio! Lorem ipsum dolor, sit amet
      consectetur adipisicing elit. Provident explicabo fugit tempore voluptatem
      reprehenderit expedita ea, tempora dolorem enim voluptates eaque nisi
      labore reiciendis iusto et repudiandae quod minima distinctio!
    </section>
  </main>
</template>

<style scoped lang="scss">
#testing {
  margin-top: 100vh;
}

.landing-content {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
}

.landing-text {
  color: white;
}

img {
  position: absolute;
  left: 0;
  top: 0;
  z-index: -1;
  width: 100%;
  height: 100vh;
  object-fit: cover;
  filter: brightness(0.25);
}

@include media-breakpoint-up(md) {
  .landing-content {
    text-align: left;
    left: 25%;
  }
}
</style>
