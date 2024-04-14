<script setup lang="ts"></script>

<template>
  <div class="flex justify-center flex-col items-center">
    <div class="relative top-12">
      <h1 class="lg:text-[120px] font-[Oswald] tracking-wide font-bold">
        <span class="text-white p-[0.2em]">Mes</span>
        <span class="stroke__projets">Experiences</span>
      </h1>
    </div>

    <div class="w-[1260px] flex justify-center relative mt-40">
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
          class="text-[28px] font-[Montserrat] font-thin lg:leading-[1] pt-3 pb-2"
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

    <div class="w-[1260px] flex justify-center relative mt-40">
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
          class="text-[28px] font-[Montserrat] font-thin lg:leading-[1] pt-3 pb-2"
        >
          Développement de nouvelles fonctionnalités sur
           https://jobs.makesense.org/fr
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
