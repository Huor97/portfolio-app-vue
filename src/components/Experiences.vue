<script setup lang="ts">
import { reactive } from "vue";
import Experience from "./Experience.vue";
import jobs from "../assets/images/jobs.avif";
import helloGolf from "../assets/images/helloGolf.jpg";
import TitleExperiencesProjects from "./TitleExperiencesProjects.vue";

const experiences = reactive([
  {
    titre: "Développeur front end",
    image: jobs,
    description: "Développement de nouvelles fonctionnalités sur ",
    link: "https://jobs.makesense.org/fr",
    technologys: ["VueJS", "NuxtJS", "VueX", "Firebase"],
    date: "Janvier - Mars 2024",
  },
  {
    titre: "Développeur front end",
    image: helloGolf,
    description:
      "J'ai réalisé des pages du site e-commerce permettant la visualisation des articles de golf.",
    technologys: ["ReactJS", "Styled Components", "API REST"],
    date: "Janvier - Mars 2022",
  },
]);
</script>

<template>
  <div class="bg-[#000] flex justify-center flex-col items-center">
    <TitleExperiencesProjects title1="Mes" title2="Expériences" />

    <template v-for="experience in experiences">
      <Experience :experience="experience" />
    </template>
  </div>
</template>

<style>
.stroke__projets {
  -webkit-text-stroke-width: 2px;
  -webkit-text-stroke-color: #ffffff;
}
</style>
