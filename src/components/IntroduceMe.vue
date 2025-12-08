<script setup lang="ts">
import BackgroundTreeSubSurface from "./BackgroundTreeSubSurface.vue";
</script>

<template>
  <BackgroundTreeSubSurface />

  <div
    class="max-sm:p-3 max-sm:top-[-7rem] md:p-10 md:top-0 lg:top-0 absolute bg-transparent z-40 mt-[270px] lg:left-20">
    <div>
      <span
        class="max-sm:text-[14px] max-sm:leading-[20px] text-[28px] text-white font-[Montserrat] font-thin tracking-wide">
        <div>Hello, c'est Rouh</div>
      </span>
    </div>
    <div class="max-sm:leading-[80px] leading-[140px] tracking-wide">
      <h1 class="max-sm:text-[60px] text-[120px] text-transparent stroke__title font-[Oswald] font-bold">
        DÉVELOPPEUR
      </h1>
      <h1 class="max-sm:text-[60px] text-[120px] font-[Oswald] font-bold text-white">
        Full Stack
      </h1>
    </div>
    <div class="max-sm:text-[14px] text-[28px] text-white font-[Montserrat] tracking-wide leading-[1.5] font-thin">
      <div>
        <span> J'aime programmer et résoudre des problèmes. </span>
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
