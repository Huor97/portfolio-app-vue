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
  <div class="bg-[#000] flex justify-center flex-col items-center">
    <div class="relative">
      <h1
        ref="quote1"
        class="max-sm:text-[50px] md:text-[100px] lg:text-[120px] font-[Oswald] tracking-wide font-bold"
      >
        <span class="text-white p-[0.2em]">Mes</span>
        <span class="stroke__projets">Experiences</span>
      </h1>
    </div>

    <div
      class="max-sm:flex-col max-sm:items-center lg:w-[1260px] flex justify-center relative mt-40"
    >
      <div class="w-[30%]">
        <img
          class="rounded-full w-[100%]"
          src="../assets/images/helloGolf.jpg"
          alt="e-comerce vent de fleur"
        />
      </div>

      <div class="ml-[30px] text-white">
        <span>Janvier - Mars 2022</span>
        <h2 class="text-[74px] leading-[74px] font-[Oswald] tracking-wide">
          Développeur
        </h2>
        <h2 class="text-[74px] leading-[74px] font-[Oswald] tracking-wide">
          front end
        </h2>
        <p
          class="max-sm:text-[18px] lg:text-[28px] font-[Montserrat] font-thin lg:leading-[1] pt-3 pb-2"
        >
          J'ai réalisé des pages du site e-commerce permettant la visualisation
          des articles de golf.
        </p>
        <div>
          <ul>
            <li>ReactJS</li>
            <li>Styled Components</li>
            <li>API REST</li>
          </ul>
        </div>
      </div>
    </div>

    <div
      class="max-sm:flex-col max-sm:items-center lg:w-[1260px] flex justify-center relative mt-40"
    >
      <div class="w-[30%]">
        <img
          class="rounded-full w-[100%]"
          src="../assets/images/jobs.avif"
          alt="e-comerce vent de fleur"
        />
      </div>

      <div class="ml-[30px] text-white">
        <span>Janvier - Mars 2024</span>
        <h2 class="text-[74px] leading-[74px] font-[Oswald] tracking-wide">
          Développeur
        </h2>
        <h2 class="text-[74px] leading-[74px] font-[Oswald] tracking-wide">
          front end
        </h2>
        <p
          class="max-sm:text-[18px] lg:text-[28px] font-[Montserrat] font-thin lg:leading-[1] pt-3 pb-2"
        >
          Développement de nouvelles fonctionnalités sur
          <a
            data-hover="true"
            href="https://jobs.makesense.org/fr"
            target="_blank"
          >
             https://jobs.makesense.org/fr
          </a>
        </p>
        <div>
          <ul>
            <li>VueJS</li>
            <li>NuxtJS</li>
            <li>VueX</li>
            <li>Firebase</li>
          </ul>
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
