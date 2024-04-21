<script setup lang="ts">
import Competences from "./Competences.vue";
import { reactive } from "vue";

const competences = reactive([
  {
    titre: " Méthode / UX/UI",
    technology: ["Agile. MVP", "UML", "Trello. Miro", "Figma"],
  },
  {
    titre: "Front-end",
    technology: [
      "HTML/CSS",
      "JavaScript/TypeScript",
      "React",
      "VueJS (Nuxt.js/VueX)",
      "ThreeJS",
      "API REST",
    ],
  },
  {
    titre: "Back-end",
    technology: ["NodeJS", "Python", "Java", "MySQL", "Firebase/Firestore"],
  },
  {
    titre: "CMS / CI/CD / OS",
    technology: [
      "WordPress",
      "GitLab/GitHub",
      "Docker",
      "Linux Debian, Fedora",
    ],
  },
]);
</script>

<template>
  <div class="bg-[#000] flex justify-center flex-col items-center">
    <div class="relative mt-72">
      <p
        class="text-white max-sm:text-[14px] text-[28px] font-[Montserrat] font-thin"
      >
        Me contacter:
      </p>
      <h1
        class="max-sm:text-[1.5rem] text-[3.75rem] text-white font-[Montserrat] tracking-wide"
      >
        <span
          ><a href="mailto:karimi.rouh@proton.me " data-hover="true"
            >karimi.rouh@proton.me</a
          ></span
        >
      </h1>
    </div>

    <div
      class="text-white md:w-[700px] lg:w-[1260px] flex max-sm:flex-wrap justify-between relative mt-52"
    >
      <template v-for="competence in competences">
        <Competences :competence="competence" />
      </template>
    </div>

    <div class="text-white font-thin relative mt-20">
      <span>© Copyright 2024 Rouh</span>
    </div>
  </div>
</template>

<style>
.stroke__projets {
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: #ffffff;
}

.hover-2 {
  background: linear-gradient(#ffffff 0 0) no-repeat calc(0% - var(--p, 0%))
    100% / 100% var(--p, 0em);
  transition: 0.2s var(--t, 0s),
    background-position 0.1s calc(0.1s - var(--t, 0s));
}
.hover-2:hover {
  --p: 100%;
  --t: 0.2s;
  color: #000000;
  font-weight: 300;
}
</style>
