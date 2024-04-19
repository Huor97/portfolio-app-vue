<script setup lang="ts">
import { onMounted, ref } from "vue";
import gsap from "gsap-trial";
import SplitText from "gsap-trial/SplitText";
import BackgroundTreeSubSurface from "./BackgroundTreeSubSurface.vue";

gsap.registerPlugin(SplitText);

const quote = ref();

onMounted(() => {
  const quoteEl = quote.value;
  if (!quoteEl) return;

  const mySplitText = new SplitText(quoteEl, { type: "words, chars" });
  const chars = mySplitText.chars;

  gsap.set(quoteEl, { perspective: 400 });

  const tl = gsap.timeline();
  tl.from(chars, {
    duration: 1.3,
    opacity: 0,
    scale: 0,
    y: 100,
    rotateX: 180,
    transformOrigin: "0% 50% -50",
    ease: "back",
    stagger: 0.01,
  });
});
</script>

<template>
  <BackgroundTreeSubSurface />

  <div
    ref="quote"
    class="max-sm:p-3 max-sm:top-[-7rem] md:p-10 md:top-0 lg:top-0 absolute bg-transparent z-40 mt-[270px] lg:left-20"
  >
    <div>
      <span
        class="max-sm:text-[14px] max-sm:leading-[20px] text-[28px] text-white font-[Montserrat] font-thin leading-[1] tracking-wide"
      >
        <div>Hello</div>
        <div>Je m'appelle Rouh</div>
      </span>
    </div>
    <div class="max-sm:leading-[80px] leading-[150px] tracking-wide">
      <h1
        class="max-sm:text-[60px] text-[120px] font-[Oswald] font-bold text-white"
      >
        FULL-STACK
      </h1>
      <h1
        class="max-sm:text-[60px] text-[120px] text-transparent stroke__title font-[Oswald] font-bold"
      >
        DÉVELOPPEUR
      </h1>
    </div>
    <div
      class="max-sm:text-[14px] text-[28px] text-white font-[Montserrat] tracking-wide leading-[1.5] font-thin"
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
