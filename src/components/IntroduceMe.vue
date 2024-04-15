<script setup lang="ts">
import BackgroundTreeSubSurface from "./BackgroundTreeSubSurface.vue";
</script>

<template>
  <BackgroundTreeSubSurface />

  <div class="absolute bg-transparent top-0 z-[9999] ml-[10rem] mt-[270px]">
    <div>
      <span class="lg:leading-[1] tracking-wide">
        <div class="text-white font-[Montserrat] lg:text-[28px] font-thin">
          Hello
        </div>
        <div class="font-[Montserrat] lg:text-[28px] text-white font-thin">
          Je m'appelle Rouh
        </div>
      </span>
    </div>
    <div class="lg:leading-[150px] tracking-wide">
      <h1 class="font-[Oswald] lg:text-[120px] font-bold text-white">
        FULL-STACK
      </h1>
      <h1 class="stroke__title font-[Oswald] lg:text-[120px] font-bold">
        DÉVELOPPEUR
      </h1>
    </div>
    <div
      class="text-white font-[Montserrat] lg:text-[28px] tracking-wide leading-[1.5] font-thin"
    >
      <div>
        <span> J'aime programmer et résoudre des problèmes </span>
      </div>
      <div>
        <span>
          <strong>Persévérant</strong> et <strong>motivé</strong>, j'aspire à
          travailler en <strong>équipe</strong> pour améliorer
        </span>
      </div>
      <div>
        <span>
          mes compétences en <strong>analyse</strong> et en
          <strong>organisation</strong>, et relever de
        </span>
      </div>
      <div>
        <span>nouveaux défis.</span>
      </div>
    </div>
  </div>
</template>

<style>
.stroke__title {
  -webkit-text-stroke-width: 2px;
  -webkit-text-stroke-color: #ffffff;
}
</style>
