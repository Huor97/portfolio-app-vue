<script setup lang="ts">
defineProps({
  experience: Object,
});
</script>

<template>
  <div
    class="max-sm:flex-col max-sm:items-center lg:w-[1260px] flex justify-center relative mt-40"
  >
    <div class="w-[30%]">
      <img
        class="rounded-full w-[100%]"
        :src="experience?.image"
        alt="e-comerce vent de fleur"
      />
    </div>

    <div class="ml-[30px] text-white">
      <span>{{ experience?.date }}</span>
      <h2 class="text-[74px] leading-[74px] font-[Oswald] tracking-wide">
        Développeur
      </h2>
      <h2 class="text-[74px] leading-[74px] font-[Oswald] tracking-wide">
        front end
      </h2>
      <p
        class="max-sm:text-[18px] lg:text-[28px] font-[Montserrat] font-thin lg:leading-[1] pt-3 pb-2"
      >
        {{ experience?.description }}
        <a data-hover="true" :href="experience?.link" target="_blank">
           {{ experience?.link }}
        </a>
      </p>
      <div>
        <ul
          v-for="(technologye, index) in experience?.technologys"
          :key="index"
        >
          <li>{{ technologye }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>
<style></style>
