<template>
  <teleport to="body">
    <canvas ref="canvas" class="js-canvas"></canvas>
  </teleport>
</template>

<script setup lang="ts">
import { onMounted, ref, onBeforeUnmount, nextTick, reactive } from "vue";

import gsap from "gsap-trial";

const canvas = ref<HTMLCanvasElement | null>(null);
let ctx: CanvasRenderingContext2D | null = null;
let width = window.innerWidth;
let height = window.innerHeight;
let mouseX = width / 2;
let mouseY = height / 2;
const circle = reactive({ radius: 10, lastX: mouseX, lastY: mouseY });
let animationFrameId: number | null = null;

const onResize = () => {
  if (!canvas.value) return;
  canvas.value.width = window.innerWidth;
  canvas.value.height = window.innerHeight;
};

const lerp = (a: number, b: number, n: number) => (1 - n) * a + n * b;

const render = () => {
  if (canvas.value && ctx) {
    // Vérification que le canvas et le contexte sont disponibles
    circle.lastX = lerp(circle.lastX, mouseX, 0.25);
    circle.lastY = lerp(circle.lastY, mouseY, 0.25);

    ctx.clearRect(0, 0, width, height);
    ctx.beginPath();
    ctx.arc(circle.lastX, circle.lastY, circle.radius, 0, Math.PI * 2, false);
    ctx.fillStyle = "#ffffff";
    ctx.fill();
    ctx.closePath();
  }

  animationFrameId = requestAnimationFrame(render);
};

const handleMouseMove = (e: MouseEvent) => {
  mouseX = e.clientX;
  mouseY = e.clientY;
};

onMounted(() => {
  // Vérifier si l'appareil est tactile

  ctx = canvas.value!.getContext("2d")!;
  canvas.value!.width = window.innerWidth;
  canvas.value!.height = window.innerHeight;

  window.addEventListener("mousemove", handleMouseMove);

  window.addEventListener("resize", onResize);

  nextTick(() => {
    const elems = document.querySelectorAll("[data-hover]");

    elems.forEach((el) => {
      el.addEventListener("mouseenter", () => enlargeCursor());
      el.addEventListener("mouseleave", () => normalizeCursor());
    });
  });

  render();
});

function handleResize() {
  width = window.innerWidth;
  height = window.innerHeight;
  if (!canvas.value) return;
  canvas.value.width = width;
  canvas.value.height = height;
}

window.addEventListener("resize", handleResize);

onBeforeUnmount(() => {
  window.removeEventListener("mousemove", handleMouseMove);
  window.removeEventListener("resize", handleResize);
  window.removeEventListener("resize", onResize);
  if (animationFrameId !== null) cancelAnimationFrame(animationFrameId);
});

function enlargeCursor() {
  gsap.to(circle, {
    duration: 0.25,
    radius: 30,
    ease: "power1.inOut",
    onComplete: render, // Appeler render à la fin de l'animation pour rafraîchir le canvas
  });
}

function normalizeCursor() {
  gsap.to(circle, {
    duration: 0.25,
    radius: 10,
    ease: "power1.inOut",
    onComplete: render, // Appeler render à la fin de l'animation pour rafraîchir le canvas
  });
}
</script>

<style scoped>
.js-canvas {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  z-index: 9999;
  pointer-events: none;
  mix-blend-mode: difference;
}
</style>
