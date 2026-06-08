<script setup lang="ts">
import BackgroundTreeSubSurface from "./BackgroundTreeSubSurface.vue";

let presentation = {
  name: `Hello, c'est Rouh`,
  post: `<h1 class="max-sm:text-[60px] text-[120px] text-transparent stroke__title font-[Oswald] font-bold">
        INGÉNIEUR </h1> 
      <h1 class="max-sm:text-[60px] text-[120px] font-[Oswald] font-bold text-white">
        Front End </h1>`,
  pitch: `Passionné par le <strong>développement web</strong>, j'apporte <strong>soin du détail</strong> et
envie de bien faire à chaque projet. Formé par l'expérimentation
et les projets concrets, je cherche un <strong>environnement</strong> où je peux
progresser vite tout en <strong>contribuant vraiment</strong>.`
}
</script>

<template>
  <div>
    <BackgroundTreeSubSurface />
    <div class="max-sm:p-3 max-sm:top-[-7rem] md:p-10 md:top-0 lg:top-0 absolute bg-transparent mt-[270px] lg:left-20">
      <div
        class="max-sm:text-[14px] max-sm:leading-[20px] text-[28px] text-white font-[Montserrat] font-thin tracking-wide">
        {{ presentation.name }}
      </div>
      <div v-html="presentation.post" class="max-sm:leading-[80px] leading-[140px] tracking-wide"></div>
      <div
        class="max-sm:text-[14px] w-1/2 text-[28px] text-white font-[Montserrat] tracking-wide leading-[1.5] font-thin">
        <span v-html="presentation.pitch"></span>
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
