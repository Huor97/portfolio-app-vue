<script setup lang="ts">
import { ref, onMounted, onUnmounted, reactive } from "vue";

const cursorOuter = ref(null);
const cursorInner = ref(null);

const coords = reactive({ x: 0, y: 0 });
let endX = 0;
let endY = 0;
let requestRef;
const isActive = ref(false);

const styles = reactive({
  cursorOuter: {
    zIndex: 999,
    position: "fixed",
    opacity: 0.4, // outerAlpha
    pointerEvents: "none",
    transition: "all 0.3s ease-out",
    width: "8px", // outerSize
    height: "8px",
    backgroundColor: "#c6c6c6",
    borderRadius: "50%",
    top: "0px",
    left: "0px",
  },
  cursorInner: {
    zIndex: 999,
    position: "fixed",
    opacity: 1,
    pointerEvents: "none",
    transition: "all 0.3s ease-out",
    width: "8px", // innerSize
    height: "8px",
    backgroundColor: "#c6c6c6",
    borderRadius: "50%",
    top: "0px",
    left: "0px",
  },
});

function updateStyles() {
  if (isActive.value) {
    styles.cursorOuter.width = "50px"; // Plus grand lorsque actif
    styles.cursorOuter.height = "50px";
    styles.cursorOuter.backgroundColor = "rgba(#c6c6c6)";
  } else {
    styles.cursorOuter.width = "8px"; // Taille normale
    styles.cursorOuter.height = "8px";
    styles.cursorOuter.backgroundColor = "rgba(#c6c6c6)";
  }
}

function animateOuterCursor(time) {
  const damping = 5; // Plus le nombre est petit, plus le curseur se déplace rapidement
  coords.x += (endX - coords.x) / damping;
  coords.y += (endY - coords.y) / damping;

  styles.cursorOuter.top = `${coords.y}px`;
  styles.cursorOuter.left = `${coords.x}px`;

  requestRef = requestAnimationFrame(animateOuterCursor);
  updateStyles();
}

onMounted(() => {
  requestRef = requestAnimationFrame(animateOuterCursor);

  const updateCursor = (event) => {
    const { clientX, clientY } = event;
    endX = clientX;
    endY = clientY + window.scrollY;
    styles.cursorInner.top = `${endY}px`;
    styles.cursorInner.left = `${clientX}px`;
  };

  document.addEventListener("mousemove", updateCursor);
  document.addEventListener("scroll", updateCursor);
  // Utiliser la délégation d'événements

  document.addEventListener(
    "mouseenter",
    (event) => {
      if (event.target.matches("a, button, input")) {
        isActive.value = true;
      }
    },
    true
  );

  document.addEventListener(
    "mouseleave",
    (event) => {
      if (event.target.matches("a, button, input")) {
        isActive.value = false;
      }
    },
    true
  );

  //   document.querySelectorAll("a, button, input").forEach((el) => {
  //     el.addEventListener("mouseenter", () => (isActive.value = true));
  //     el.addEventListener("mouseleave", () => (isActive.value = false));
  //   });
});

onUnmounted(() => {
  cancelAnimationFrame(requestRef);
  document.removeEventListener("mousemove", updateCursor);
  document.removeEventListener("scroll", updateCursor);
});
</script>
<template>
  <div>
    <div ref="cursorOuter" :style="styles.cursorOuter"></div>
    <div ref="cursorInner" :style="styles.cursorInner"></div>
  </div>
</template>

<style></style>
