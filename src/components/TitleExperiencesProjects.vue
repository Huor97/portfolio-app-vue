<script setup lang="ts">
import { onMounted, ref } from "vue";
import gsap from "gsap-trial";
import ScrollTrigger from "gsap-trial/ScrollTrigger";
import SplitText from "gsap-trial/SplitText";

defineProps<{
  title1: string;
  title2: string;
}>();

gsap.registerPlugin(SplitText, ScrollTrigger);

const quote = ref();

onMounted(() => {
  const quoteEl = quote.value;
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
  <div class="relative">
    <h1
      ref="quote"
      class="max-sm:text-[50px] md:text-[100px] lg:text-[120px] font-[Oswald] tracking-wide font-bold"
    >
      <span class="text-white p-[0.2em]">{{ title1 }}</span>
      <span class="stroke__projets">{{ title2 }}</span>
    </h1>
  </div>
</template>

<style></style>
