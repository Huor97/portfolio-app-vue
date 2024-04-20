<script setup lang="ts">
import { onMounted, ref } from "vue";
import gsap from "gsap-trial";
import ScrollTrigger from "gsap-trial/ScrollTrigger";
import SplitText from "gsap-trial/SplitText";

gsap.registerPlugin(SplitText, ScrollTrigger);

const quote1 = ref();

onMounted(() => {
  const quoteEl = quote1.value;
  if (!quoteEl) return;

  const split = new SplitText(quoteEl, { type: "words, chars" });
  const chars = split.chars;

  gsap.set(chars, { opacity: 0, y: 20 });

  ScrollTrigger.create({
    trigger: quoteEl,
    start: "top 75%",
    onEnter: () => {
      gsap.to(chars, {
        duration: 1.3,
        opacity: 1,
        y: 100,
        transformOrigin: "0% 50% -50 ",
        stagger: 0.04,
        ease: "back",
      });
    },
  });
});
</script>

<template>
  <div
    class="relative bg-transparent flex justify-center flex-col items-center"
  >
    <div class="relative">
      <h1
        ref="quote1"
        class="max-sm:text-[50px] md:text-[100px] lg:text-[120px] font-[Oswald] tracking-wide font-bold"
      >
        <span class="stroke__projets p-[0.2em]">Projets</span>
        <span class="text-white">apressier</span>
      </h1>
    </div>

    <div
      class="max-sm:flex-col overflow-hidden lg:w-[1260px] flex justify-center relative mt-40"
    >
      <div
        class="max-sm:w-[425px] md:w-[500px] lg:w-[855px] hover:scale-125 duration-700"
      >
        <img
          src="../assets/images/vent-de-fleur.webp"
          alt="e-comerce vent de fleur"
        />
      </div>

      <div
        data-speed="1.1"
        class="bg-transparent md:w-[250px] lg:w-[356px] ml-[30px] text-white"
      >
        <h2 class="text-[74px] leading-[74px] font-[Oswald] tracking-wide">
          Vente de fleurs
        </h2>
        <p
          class="max-sm:text-[18px] lg:text-[28px] font-[Montserrat] font-thin lg:leading-[1] pt-3 pb-2"
        >
          J’ai conçu et réalisé ce projet en équipe, en mode Agile/MVP. Le front
          utilise ReactJS, HTML, CSS (Tailwind CSS) et le back est en NodeJS,
          MongoDB et JWT/token.
        </p>
        <div class="flex gap-[1em]">
          <a
            href="https://wonderflower.vercel.app/"
            target="_blank"
            class="font-[Montserrat] flex items-center gap-1"
            data-hover="true"
            >Site
            <svg width="14" height="14" view-box="0 0 14 14">
              <path
                d="M10.8101 1.96222L0.726954 12.0453L1.66171 12.9801L11.7448 2.89698L11.9344 9.4447L13.208 9.07311L13.0134 2.35278C12.9877 1.46249 12.2434 0.718185 11.3531 0.692412L4.80762 0.502924L4.43487 1.77539L10.8101 1.96222Z"
                fill="white"
                stroke="white"
                stroke-width="0.542084"
              ></path>
            </svg>
          </a>

          <a
            href="https://github.com/adatechschool/projet_collectif_vente_de_fleurs-FRONTEND"
            target="_blank"
            class="font-[Montserrat] flex items-center gap-1"
            data-hover="true"
            >GitHub

            <svg width="14" height="14" view-box="0 0 14 14">
              <path
                d="M10.8101 1.96222L0.726954 12.0453L1.66171 12.9801L11.7448 2.89698L11.9344 9.4447L13.208 9.07311L13.0134 2.35278C12.9877 1.46249 12.2434 0.718185 11.3531 0.692412L4.80762 0.502924L4.43487 1.77539L10.8101 1.96222Z"
                fill="white"
                stroke="white"
                stroke-width="0.542084"
              ></path>
            </svg>
          </a>
        </div>
      </div>
    </div>

    <div
      class="max-sm:flex-col overflow-hidden lg:w-[1260px] flex justify-center relative mt-40"
    >
      <div
        class="max-sm:w-[425px] md:w-[500px] lg:w-[855px] hover:scale-125 duration-700"
      >
        <img
          src="../assets/images/suivi-de-cycle-menstruel.webp"
          alt="e-comerce vent de fleur"
        />
      </div>

      <div
        data-speed="1.1"
        class="lg:w-[356px] md:w-[250px] ml-[30px] text-white"
      >
        <h2 class="text-[74px] leading-[74px] font-[Oswald] tracking-wide">
          Suivi de cycle menstruel
        </h2>
        <p
          class="max-sm:text-[18px] lg:text-[28px] font-[Montserrat] font-thin lg:leading-[1] pt-3 pb-2"
        >
          Cette application mobile est un projet d’équipe utilisant en front
          React Native et en back PostgreSQL et une API, via Supabase.
        </p>
        <div class="flex gap-[1em]">
          <a
            href="https://github.com/adatechschool/NeverLeak_front"
            target="_blank"
            class="font-[Montserrat] flex items-center gap-1"
            data-hover="true"
            >GitHub

            <svg width="14" height="14" view-box="0 0 14 14">
              <path
                d="M10.8101 1.96222L0.726954 12.0453L1.66171 12.9801L11.7448 2.89698L11.9344 9.4447L13.208 9.07311L13.0134 2.35278C12.9877 1.46249 12.2434 0.718185 11.3531 0.692412L4.80762 0.502924L4.43487 1.77539L10.8101 1.96222Z"
                fill="white"
                stroke="white"
                stroke-width="0.542084"
              ></path>
            </svg>
          </a>
        </div>
      </div>
    </div>

    <div
      class="max-sm:flex-col overflow-hidden lg:w-[1260px] flex justify-center relative mt-40"
    >
      <div
        class="max-sm:w-[425px] md:w-[500px] lg:w-[855px] hover:scale-125 duration-700"
      >
        <img
          src="../assets/images/portfolio3d.webp"
          alt="e-comerce vent de fleur"
        />
      </div>

      <div
        data-speed="1.1"
        class="md:w-[250px] lg:w-[356px] ml-[30px] text-white"
      >
        <h2 class="text-[74px] leading-[74px] font-[Oswald] tracking-wide">
          Portfolio Parallaxe
        </h2>
        <p
          class="max-sm:text-[18px] lg:text-[28px] font-[Montserrat] font-thin lg:leading-[1] pt-3 pb-2"
        >
          J'ai découvert puis utilisé React Drei et Three Fiber pour intégrer de
          l'interactivité 3D de Three.js. Hébergé sur Vercel, bientôt sur AWS.
        </p>
        <div class="flex gap-[1em]">
          <a
            href="https://portfolio-rouh.vercel.app/"
            target="_blank"
            class="font-[Montserrat] flex items-center gap-1"
            data-hover="true"
            >Site
            <svg width="14" height="14" view-box="0 0 14 14">
              <path
                d="M10.8101 1.96222L0.726954 12.0453L1.66171 12.9801L11.7448 2.89698L11.9344 9.4447L13.208 9.07311L13.0134 2.35278C12.9877 1.46249 12.2434 0.718185 11.3531 0.692412L4.80762 0.502924L4.43487 1.77539L10.8101 1.96222Z"
                fill="white"
                stroke="white"
                stroke-width="0.542084"
              ></path>
            </svg>
          </a>

          <a
            href="https://github.com/Huor97/portfolio"
            target="_blank"
            class="font-[Montserrat] flex items-center gap-1"
            data-hover="true"
            >GitHub

            <svg width="14" height="14" view-box="0 0 14 14">
              <path
                d="M10.8101 1.96222L0.726954 12.0453L1.66171 12.9801L11.7448 2.89698L11.9344 9.4447L13.208 9.07311L13.0134 2.35278C12.9877 1.46249 12.2434 0.718185 11.3531 0.692412L4.80762 0.502924L4.43487 1.77539L10.8101 1.96222Z"
                fill="white"
                stroke="white"
                stroke-width="0.542084"
              ></path>
            </svg>
          </a>
        </div>
      </div>
    </div>

    <div
      class="max-sm:flex-col overflow-hidden lg:w-[1260px] flex justify-center relative mt-40"
    >
      <div
        class="max-sm:w-[425px] md:w-[500px] lg:w-[855px] hover:scale-125 duration-700"
      >
        <img
          src="../assets/images/portfolio1.webp"
          alt="e-comerce vent de fleur"
        />
      </div>

      <div
        data-speed="1.1"
        class="md:w-[250px] lg:w-[356px] ml-[30px] text-white"
      >
        <h2 class="text-[74px] leading-[74px] font-[Oswald] tracking-wide">
          Portfolio React
        </h2>
        <p
          class="max-sm:text-[18px] lg:text-[28px] font-[Montserrat] font-thin lg:leading-[1] pt-3 pb-2"
        >
          Mon premier portfolio responsive en React, GSAP, HTML, CSS(SCSS) sous
          Vercel et incluant un formulaire de contact.
        </p>
        <div class="flex gap-[1em]">
          <a
            href="https://portfolio-huor97.vercel.app/"
            target="_blank"
            class="font-[Montserrat] flex items-center gap-1"
            data-hover="true"
            >Site
            <svg width="14" height="14" view-box="0 0 14 14">
              <path
                d="M10.8101 1.96222L0.726954 12.0453L1.66171 12.9801L11.7448 2.89698L11.9344 9.4447L13.208 9.07311L13.0134 2.35278C12.9877 1.46249 12.2434 0.718185 11.3531 0.692412L4.80762 0.502924L4.43487 1.77539L10.8101 1.96222Z"
                fill="white"
                stroke="white"
                stroke-width="0.542084"
              ></path>
            </svg>
          </a>

          <a
            href="https://github.com/Huor97/portfolio"
            target="_blank"
            class="font-[Montserrat] flex items-center gap-1"
            data-hover="true"
            >GitHub

            <svg width="14" height="14" view-box="0 0 14 14">
              <path
                d="M10.8101 1.96222L0.726954 12.0453L1.66171 12.9801L11.7448 2.89698L11.9344 9.4447L13.208 9.07311L13.0134 2.35278C12.9877 1.46249 12.2434 0.718185 11.3531 0.692412L4.80762 0.502924L4.43487 1.77539L10.8101 1.96222Z"
                fill="white"
                stroke="white"
                stroke-width="0.542084"
              ></path>
            </svg>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.stroke__projets {
  -webkit-text-stroke-width: 2px;
  -webkit-text-stroke-color: #ffffff;
}
</style>
