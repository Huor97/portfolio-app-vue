<script setup lang="ts">
defineProps({
  projet: Object,
});
</script>

<template>
  <div
    class="max-sm:flex-col overflow-hidden lg:w-[1260px] flex justify-center relative mt-40"
  >
    <div
      class="max-sm:w-[425px] md:w-[500px] lg:w-[855px] hover:scale-125 duration-700"
    >
      <img :src="projet?.image" alt="e-comerce vent de fleur" />
    </div>

    <div
      data-speed="1.1"
      class="bg-transparent md:w-[250px] lg:w-[356px] ml-[30px] text-white"
    >
      <h2 class="text-[74px] leading-[74px] font-[Oswald] tracking-wide">
        {{ projet?.titre }}
      </h2>
      <p
        class="max-sm:text-[18px] lg:text-[28px] font-[Montserrat] font-thin lg:leading-[1] pt-3 pb-2"
      >
        {{ projet?.description }}
      </p>
      <div class="flex gap-[1em]">
        <a
          v-if="projet?.site != ''"
          :href="projet?.site"
          target="_blank"
          class="font-[Montserrat] flex items-center gap-1"
          data-hover="true"
          >Site
          <svg width="14" height="14" view-box="0 0 14 14">
            <path
              d="M10.8101 1.96222L0.726954 12.0453L1.66171 12.9801L11.7448 2.89698L11.9344 9.4447L13.208 9.07311L13.0134 2.35278C12.9877 1.46249 12.2434 0.718185 11.3531 0.692412L4.80762 0.502924L4.43487 1.77539L10.8101 1.96222Z"
              fill="white"
              stroke="white"
              stroke-width="0.542084"
            ></path>
          </svg>
        </a>

        <a
          :href="projet?.github"
          target="_blank"
          class="font-[Montserrat] flex items-center gap-1"
          data-hover="true"
          >GitHub

          <svg width="14" height="14" view-box="0 0 14 14">
            <path
              d="M10.8101 1.96222L0.726954 12.0453L1.66171 12.9801L11.7448 2.89698L11.9344 9.4447L13.208 9.07311L13.0134 2.35278C12.9877 1.46249 12.2434 0.718185 11.3531 0.692412L4.80762 0.502924L4.43487 1.77539L10.8101 1.96222Z"
              fill="white"
              stroke="white"
              stroke-width="0.542084"
            ></path>
          </svg>
        </a>
      </div>
    </div>
  </div>
</template>

<style></style>
