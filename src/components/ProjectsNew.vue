<script setup lang="ts">
import { reactive } from "vue";
import Project from "./Project.vue";
import faverton from "../assets/images/faverton.png";
import claudiaEvaluation from "../assets/images/claudia-evaluation.png"
import TitleExperiencesProjects from "./TitleExperiencesProjects.vue";

const newProjects = reactive([
    {
        titre: "Faverton",
        image: faverton,
        description:
            "Application d'évaluation de potentiel photovoltaïque. Outil accessible pour accélérer la transition énergétique. Nuxt 3, Supabase, Dockerisé. Suppression des données conforme au RGPD",
        site: "https://favertons.favian.eu",
        github:
            "https://github.com/Huor97/faverton-app",
    },
    {
        titre: "claudIA évaluation",
        image: claudiaEvaluation,
        description:
            "claudIA.évaluation est une application web propulsée par l'IA (Mistral) qui agit comme un tuteur de français. Elle permet aux utilisateurs de soumettre des textes et de recevoir des corrections détaillées adaptées à leur niveau de langue (de A1 à Natif).",
        site: "https://claud-ia.opensive.fr/",
        github: "",
    }
]);
</script>

<template>
    <div class="relative bg-transparent flex justify-center flex-col items-center">
        <TitleExperiencesProjects title1="Projets" title2="actuels" />
        <template v-for="projet in newProjects" :key="projet.titre">
            <Project :projet="projet" />
        </template>
    </div>
</template>
