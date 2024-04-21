<script setup lang="ts">
import { reactive } from "vue";
import Project from "./Project.vue";
import ventDeFleur from "../assets/images/vent-de-fleur.webp";
import suiviDeCycleMenstruel from "../assets/images/suivi-de-cycle-menstruel.webp";
import portfolio3D from "../assets/images/portfolio3d.webp";
import portfolio1 from "../assets/images/portfolio1.webp";
import TitleExperiencesProjects from "./TitleExperiencesProjects.vue";

const projets = reactive([
  {
    titre: "Vente de fleurs",
    image: ventDeFleur,
    description:
      "J’ai conçu et réalisé ce projet en équipe, en mode Agile/MVP. Le front utilise ReactJS, HTML, CSS (Tailwind CSS) et le back est en NodeJS, MongoDB et JWT/token.",
    site: "https://wonderflower.vercel.app/",
    github:
      "https://github.com/adatechschool/projet_collectif_vente_de_fleurs-FRONTEND",
  },
  {
    titre: "Suivi de cycle menstruel",
    image: suiviDeCycleMenstruel,
    description:
      "Cette application mobile est un projet d’équipe utilisant en front React Native et en back PostgreSQL et une API, via Supabase.",
    site: "",
    github: "https://github.com/adatechschool/NeverLeak_front",
  },
  {
    titre: "Portfolio Parallaxe",
    image: portfolio3D,
    description:
      "J'ai découvert puis utilisé React Drei et Three Fiber pour intégrer de l'interactivité 3D de Three.js. Hébergé sur Vercel.",
    site: "https://portfolio-rouh.vercel.app/",
    github: "https://github.com/Huor97/portfolio-parallax",
  },
  {
    titre: "Portfolio React",
    image: portfolio1,
    description:
      "Mon premier portfolio responsive en React, GSAP, HTML, CSS(SCSS) sous Vercel et incluant un formulaire de contact.",
    site: "https://portfolio-huor97.vercel.app/",
    github: "https://github.com/Huor97/portfolio",
  },
]);
</script>

<template>
  <div
    class="relative bg-transparent flex justify-center flex-col items-center"
  >
    <TitleExperiencesProjects title1="Projets" title2="choisi" />
    <template v-for="projet in projets">
      <Project :projet="projet" />
    </template>
  </div>
</template>

<style>
.stroke__projets {
  -webkit-text-stroke-width: 2px;
  -webkit-text-stroke-color: #ffffff;
}
</style>
