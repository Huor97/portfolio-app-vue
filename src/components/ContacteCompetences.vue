<script setup lang="ts"></script>

<template>
  <div class="bg-[#000] flex justify-center flex-col items-center">
    <div class="relative mt-72">
      <p
        class="text-white max-sm:text-[14px] text-[28px] font-[Montserrat] font-thin"
      >
        travailler avec moi:
      </p>
      <h1
        class="max-sm:text-[1.5rem] text-[3.75rem] text-white font-[Montserrat] tracking-wide"
      >
        <span
          ><a href="mailto:karimi.rouh@proton.me " data-hover="true"
            >karimi.rouh@proton.me</a
          ></span
        >
      </h1>
    </div>

    <div
      class="text-white md:w-[700px] lg:w-[1260px] flex max-sm:flex-wrap justify-between relative mt-52"
    >
      <div class="max-sm:basis-1/2 max-sm:w-1/2">
        <div
          class="font-[montserrat] border-solid border-b-2 border-b-white-500 mb-4"
        >
          Méthode / UX/UI
        </div>

        <div>
          <ul class="font-[montserrat] font-thin">
            <li class="hover-2">Agile. MVP</li>

            <li class="hover-2">UML</li>
            <li class="hover-2">Trello. Miro</li>
            <li class="hover-2">Figma</li>
          </ul>
        </div>
      </div>

      <div class="max-sm:basis-1/2 max-sm:w-1/2">
        <div
          class="font-[montserrat] border-solid border-b-2 border-b-white-500 mb-4"
        >
          Front-end
        </div>
        <div>
          <ul class="font-[montserrat] font-thin">
            <li class="hover-2">HTML/CSS</li>
            <li class="hover-2">JavaScript/TypeScript</li>
            <li class="hover-2">React</li>
            <li class="hover-2">VueJs (Nuxt.js/VueX)</li>
            <li class="hover-2">ThreeJS</li>
            <li class="hover-2">API REST</li>
          </ul>
        </div>
      </div>

      <div class="max-sm:basis-1/2 max-sm:w-1/2">
        <div
          class="font-[montserrat] border-solid border-b-2 border-b-white-500 mb-4"
        >
          Back-end
        </div>
        <div>
          <ul class="font-[montserrat] font-thin">
            <li class="hover-2">NodeJS</li>
            <li class="hover-2">Python</li>
            <li class="hover-2">Java</li>
            <li class="hover-2">MySQL</li>
            <li class="hover-2">Firebase/Firestore</li>
          </ul>
        </div>
      </div>

      <div class="max-sm:basis-1/2 max-sm:w-1/2">
        <div
          class="font-[montserrat] border-solid border-b-2 border-b-white-500 mb-4"
        >
          CMS / CI/CD / OS
        </div>
        <div>
          <ul class="font-[montserrat] font-thin">
            <li class="hover-2">WordPress</li>
            <li class="hover-2">GitLab/GitHub</li>
            <li class="hover-2">Docker</li>
            <li class="hover-2">Linux Debian, Fedora</li>
          </ul>
        </div>
      </div>
    </div>

    <div class="text-white font-thin relative mt-20">
      <span>© Copyright 2024 Rouh</span>
    </div>
  </div>
</template>

<style>
.stroke__projets {
  -webkit-text-stroke-width: 1px;
  -webkit-text-stroke-color: #ffffff;
}

.hover-2 {
  background: linear-gradient(#ffffff 0 0) no-repeat calc(0% - var(--p, 0%))
    100% / 100% var(--p, 0em);
  transition: 0.2s var(--t, 0s),
    background-position 0.1s calc(0.1s - var(--t, 0s));
}
.hover-2:hover {
  --p: 100%;
  --t: 0.2s;
  color: #000000;
  font-weight: 300;
}
</style>
