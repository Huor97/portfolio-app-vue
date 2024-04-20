<script setup lang="ts">
import MenuNav from "./components/MenuNav.vue";
import IntroducMe from "./components/IntroduceMe.vue";
import Project from "./components/Project.vue";
import Experience from "./components/Experience.vue";
import ContacteCompetences from "./components/ContacteCompetences.vue";
import { onMounted, onUnmounted, ref } from "vue";
import CursorAnimation from "./components/CursorAnimation.vue";
import gsap from "gsap-trial";
import { ScrollTrigger } from "gsap-trial/ScrollTrigger";
import ScrollSmoother from "gsap-trial/ScrollSmoother";

gsap.registerPlugin(ScrollTrigger, ScrollSmoother);

const main = ref<HTMLElement | null>(null);

let ctx: gsap.Context | undefined;

onMounted(() => {
  // ctx est un context qui signifie un conteneur qui encapsule un ensemble d'animation
  if (main.value) {
    ctx = gsap.context(() => {
      ScrollSmoother.create({
        smooth: 2,
        effects: true,
      });
    }, main.value);
  } else {
    console.error("L'élément 'main' n'a pas été trouvé");
  }
});

onUnmounted(() => {
  ctx?.revert();
});
</script>

<template>
  <div ref="main">
    <CursorAnimation />
    <MenuNav />
    <IntroducMe />
    <Project />
    <Experience />
    <ContacteCompetences />
  </div>
</template>

<style scoped></style>
