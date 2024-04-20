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

const main = ref();

let smoother;
let ctx: gsap.Context | undefined;

onMounted(() => {
  // ctx est un context qui signifie un conteneur qui encapsule un ensemble d'animation
  ctx = gsap.context(() => {
    smoother = ScrollSmoother.create({
      smooth: 2,
      effects: true,
    });
  }, main.value);
});

onUnmounted(() => {
  ctx?.revert();
});
</script>

<template>
  <div>
    <CursorAnimation />
    <MenuNav />
    <IntroducMe />
    <Project />
    <Experience />
    <ContacteCompetences />
  </div>
</template>

<style scoped></style>
